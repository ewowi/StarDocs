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
    Coord3D testCoord3D = leds.sharedData.read<Coord3D>();

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
    ui->initCoord3D(parentVar, "testCoord3D", leds.sharedData.write<Coord3D>({1,2,3}));
  }
}; // ExampleEffect
```
(updated June 4, 2024)

Remarks

* Updated!: An effect should run fine on any dimension of a fixture (1D/2D/3D) of any size (including 0,0,0 or 1,1,1).
    * An effect has no notion of the physical shape of the fixture the effect will be projected on.
    * The only information an effect has is leds.projectionDimension and leds.isMapped(Coord3D).
    * An effect has a default effect dimension (dim(), but the projection functions in StarLeds will deal with properly displaying an effect on a fixture.
    * An effect can use leds.projectionDimension to make it optimized for 1D, 2D and 3D, no need to create different effects for different dimensions (e.g. fire 1D, 2D and 3D can all be in one effect).
    * See the Game of Life effect for an advanced effect using leds.projectionDimension and leds.isMapped(Coord3D)
    * See also [Projections And Mappings](/StarDocs/StarLeds/ProjectionsAndMappings)
* Effects should be written in a way it supports any dimension including 1:1:1 and 0:0:0 (exotic projections do rely on this).
* name(), dim() and tags() provide effect metadata
* leds.sharedData preserves data over multiple loops, in case of array add the number of elements. data allocation and management will be done transparent from the effect code.
* leds.size is the virtual size of the effect
* leds[pos] = color gives a virtual pixel a value
* leds[pos] = color is identical to leds.setPixelColor(pos, color);
* color = leds[pos] is identical to color = leds.getPixelColor(pos);
* FastLed library commands can be used. e.g. leds.fill_solid(CRGB::Black); operations will be executed in the virtual leds context
* Effect class should not contain public or private variables, use return functions instead to minimize memory foodprint
* use sys->now instead of millis() as it supports syncing with other instances, random16_set_seed(sys->now) is provided under the hood for predictable execution of effects using the random function (however wip)
