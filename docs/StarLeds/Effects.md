---
title: Effects
hide:
  # - navigation
  # - toc
---

## Effects

Text

## Dev

```
class ExampleEffect: public Effect {
public:
  const char * name() {return "ExampleEffect";}
  unsigned8 dim() {return _2D;}
  const char * tags() {return "♪♫⚡💡💫";}

  void setup(Leds &leds) {
    leds.fill_solid(CRGB::Black);
  }

  void loop(Leds &leds) {

    CRGBPalette16 pal = getPalette();
    stackUnsigned8 speed = mdl->getValue("speed");
    stackUnsigned8 legs = mdl->getValue("legs");

    map_t    *rMap = leds.sharedData.bind(rMap, leds.size.x * leds.size.y); //array
    uint8_t *offsX = leds.sharedData.bind(offsX);
    uint16_t *aux0 = leds.sharedData.bind(aux0);

    Coord3D pos = {0,0,0};

    for (pos.x = 0; pos.x < leds.size.x; pos.x++) {
      for (pos.y = 0; pos.y < leds.size.y; pos.y++) {
        CRGB color = ColorFromPalette(pal, radius, intensity);
        leds[pos] = color; // or setPixelColor(pos, color);
      }
    }
  }

  void controls(JsonObject parentVar) {
    addPalette(parentVar, 4);
    ui->initSlider(parentVar, "speed", 128, 1, 255);
    ui->initSlider(parentVar, "legs", 4, 1, 8);
  }
}; // ExampleEffect
```

* name(), dim() and tags() provide effect metadata
* leds.sharedData.bind() preserves data over multiple loops, in case of array add the number of elements. .bind is the only command needed, data allocation and management will be done transparent from the effect code.
* leds.size is the virtual size of the effect
* leds[pos] = color gives a virtual pixel a value
* leds[pos] = color is identical to leds.setPixelColor(pos, color);
* color = leds[pos] is identical to color = leds.getPixelColor(pos);
* FastLed library commands can be used. e.g. leds.fill_solid(CRGB::Black); operations will be executed in the virtual leds context

Notes:

* Effect class may not contain vars, use return functions instead to minimize memory foodprint

### See also

* [Projections And Mappings](/StarDocs/StarLeds/ProjectionsAndMappings) : virtual to physical mapping of an effect
