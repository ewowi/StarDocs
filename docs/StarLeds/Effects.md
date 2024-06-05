---
title: Effects
hide:
  # - navigation
  # - toc
---

## Effects

StarLeds comes with a range of built in lighting effects. Users can also create their own effects in the LedEffects.h file.

## Effect Types

Effects can be specific to a type of fixture, such as 2D or 3D effects. Effects can be synchronized between multiple instances of StarLeds.

## Creating New Effects

The procedure for creating a new effect is easy:

1. Copy the Effect Template found on this page into "src/App/LedEffects.h".
2. Rename the "ExampleEffect" in both locations (2 top, 1 bottom) within the template.
3. Add it to the appropriate location "class Effects {}" near the bottom of the file.

This is sufficient for the new effect to run and be selectable.

## Effects Basics

Addressing LEDs

1. "leds.size" is the virtual size of the effect.
2. "leds[pos] = color" gives a virtual pixel a color value. Identical to "leds.setPixelColor(pos, color)"
3. "color = leds[pos]" 
4. Colors can be an HSV or RGB value. RGB is intuitive as it relates to the LED hardware. HSV is often simpler for programming effects.
5. Colors can be applied directly from a palette: "ColorFromPalette( const CRGBPalette16& pal, uint8_t index, uint8_t brightness, TBlendType blendType)"

## FastLED commands

StarLeds runs on [FastLED](https://github.com/FastLED/FastLED). FastLED's [documentation](http://fastled.io/docs/modules.html) has more information about the wide range of options available for programming LEDs.

🚧

## Genral Approaches to Creating an Effect

🚧

## Effect Example

This template can be used to create new effects. The settings are explained below:

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
```

Remarks

* There is no notion of the physical shape of the fixture the effect will be projected on. An effect has a dimension but the projection functions in StarLeds will deal with properly displaying an effect on a fixture. See [Projections And Mappings](/StarDocs/StarLeds/ProjectionsAndMappings)
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

## Annotated Effect Template

🚧

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


