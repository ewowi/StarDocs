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
  uint8_t dim() {return _2D;}
  const char * tags() {return "♪♫⚡💡💫";}

  void setup(Leds &leds) {
    leds.fill_solid(CRGB::Black);
  }

  void loop(Leds &leds) {
    //Binding of controls. Keep before binding of vars and keep in same order as in controls()
    uint8_t speed = leds.sharedData.read<uint8_t>();
    uint8_t legs = leds.sharedData.read<uint8_t>();

    //binding of loop persistent values (pointers) tbd: aux0,1,step etc can be renamed to meaningful names
    map_t    *rMap = leds.sharedData.readWrite<map_t>(leds.size.x * leds.size.y); //array
    uint8_t *offsX = leds.sharedData.readWrite<uint8_t>();
    uint16_t *aux0 = leds.sharedData.readWrite<uint16_t>();

    unsigned long beatTimer = sys->now - *step;

    Coord3D pos = {0,0,0};

    for (pos.x = 0; pos.x < leds.size.x; pos.x++) {
      for (pos.y = 0; pos.y < leds.size.y; pos.y++) {
        CRGB color = ColorFromPalette(leds.palette, random8());
        leds[pos] = color; // or setPixelColor(pos, color);
      }
    }
  }

  void controls(JsonObject parentVar) {
    Effect::controls(leds, parentVar);
    ui->initSlider(parentVar, "speed", leds.sharedData.write<uint8_t>(128), 1, 255);
    ui->initSlider(parentVar, "legs", leds.sharedData.write<uint8_t>(4), 1, 8);
  }
}; // ExampleEffect
```
(updated June 4, 2024)

* name(), dim() and tags() provide effect metadata
* leds.sharedData preserves data over multiple loops, in case of array add the number of elements. data allocation and management will be done transparent from the effect code.
* leds.size is the virtual size of the effect
* leds[pos] = color gives a virtual pixel a value
* leds[pos] = color is identical to leds.setPixelColor(pos, color);
* color = leds[pos] is identical to color = leds.getPixelColor(pos);
* FastLed library commands can be used. e.g. leds.fill_solid(CRGB::Black); operations will be executed in the virtual leds context
* use sys->now instead of millis() as it supports syncing with other instances, random16_set_seed(sys->now) is provided under the hood for predictable execution of effects (however wip)

Notes:

* Effect class should not contain vars, use return functions instead to minimize memory foodprint

### See also

* [Projections And Mappings](/StarDocs/StarLeds/ProjectionsAndMappings) : virtual to physical mapping of an effect
