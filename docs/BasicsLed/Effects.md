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
class Exampleeffect: public Effect {
public:
  const char * name() {return "Octopus";}
  unsigned8 dim() {return _2D;}
  const char * tags() {return "💡";}

  void loop(Leds &leds) {

    CRGBPalette16 pal = getPalette();
    stackUnsigned8 speed = mdl->getValue("speed");
    stackUnsigned8 legs = mdl->getValue("Legs");

    map_t    *rMap = leds.sharedData.bind(rMap, leds.size.x * leds.size.y); //array
    uint8_t *offsX = leds.sharedData.bind(offsX);
    uint16_t *aux0 = leds.sharedData.bind(aux0);

    Coord3D pos = {0,0,0};

    for (pos.x = 0; pos.x < leds.size.x; pos.x++) {
      for (pos.y = 0; pos.y < leds.size.y; pos.y++) {
        CRGB color = ColorFromPalette(pal, *step / 2 - radius, intensity);
        leds[pos] = color;
      }
    }
  }
  void controls(JsonObject parentVar) {
    addPalette(parentVar, 4);

    ui->initSlider(parentVar, "speed", 128, 1, 255);
    ui->initSlider(parentVar, "Legs", 4, 1, 8);
  }
}; // Exampleeffect
```

* name(), dim() and tags() provide effect metadata

* leds.sharedData.bind() preserves data over multiple loops

* leds.size is the virtual size of the effect

* leds[pos] = color gives a virtual pixel a value

### See also

* [Projections And Mappings](/StarDocs/BasicsLed/ProjectionsAndMappings) : virtual to physical mapping of an effect
