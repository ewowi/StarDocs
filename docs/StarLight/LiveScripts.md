---
title: Live Scripts
hide:
  # - navigation
  # - toc
---

<img width="450" alt="image" src="https://github.com/user-attachments/assets/418fb6ee-3580-456e-97e0-9344a0d13fac">

## Introduction

StarLight supports Live Effects, Live Fixtures and Live Projections. These exists next to normal effects (coded in c++), normal fixtures (generated or manually created as F_ixture.json files) and normal projections (coded in c++). Normal effects and normal projections are part of a specific build of StarLight and are fixed within that build. Normal fixtures can be created by an end user of StarLight.
The Live versions can all be created by an end user at any time and executed in StarLight.

### Live Effects

Live Effects are effects implemented by a script on the ESP32 filesystem ([Files Module](/StarDocs/SysMod/SysModFiles)). Live scripts are pseudo c-code files which are parsed and compiled into assembler and runs at very high speed (like compiled c-code!) without rebooting or flashing!!! Live effects are a specific application of Live Scripts (see [StarBase Live Scripts Module](/StarDocs/UserMod/UserModLiveScripts)).

* A Live Effect can be executed by selecting Live Effect in the [Effects Module](/StarDocs/StarLightMod/StarLightModEffects/).

* Next a script can be selected with the .sc file extension. After selection the file will be executed directly:

    <img width="362" alt="image" src="https://github.com/user-attachments/assets/de946239-6ad7-4df5-bbd1-92e484be57f0">

* Optionally Slider1, 2, or 3 controls can be used to change the behaviour of the effect (in future release slider types and names can be defined in the live script itself).

* Example(s) of Live Effect scripts can be found in [StarLight repo/misc/LiveScripts](https://github.com/MoonModules/StarLight/tree/main/misc/LiveScripts)

<img width="550" alt="image" src="https://github.com/user-attachments/assets/db350093-56f2-47d1-b9ed-a8c1c5f978bd">

### StarLight Live functions
Supported StarLight functions to be used in scripts

    CRGB    hsv(uint8_t hue, uint8_t saturation, uint8_t value); //HSV Color
    CRGB    rgb (uint8_t red, uint8_t green, uint8_t blue); //RGB color
    uint8_t beatSin8 (uint8_t bpm, uint8_t lowest, uint8_t highest) Beats per minute 
    uint8_t inoise8 (uint16_t x, uint16_t y, uint16_t z) xyz coordinate on noise map (3D)
    uint8_t random8(); //random between 0 and 255
    uint8_t sin8(uint8_t theta); //theta input angle from 0-255, results 0-255
    uint8_t cos8(uint8_t theta); //theta input angle from 0-255, results 0-255
    void    sPC(uint16_t pixel, CRGB color); //setPixelColor
    void    sCFP(uint16_t pixel, uint8_t color index, uint8_t brightness); //Set Color From Palette
    void    fadeToBlackBy(uint8_t fadeBy)

* plus [StarBase Live functions](/StarDocs/UserMod/UserModLiveScripts/#starbase-live-functions)
* more functions will be available later, new functions can be requested in [Github issues](https://github.com/MoonModules/StarLight/issues).


### Preparing and running Live Effects

* See [Preparing live scripts](/StarDocs/UserMod/UserModLiveScripts/#preparing-live-scripts) and [Running live scripts](/StarDocs/UserMod/UserModLiveScripts/#running-a-live-script)

## Live Fixtures

Live Fixtures are fixture definitions implemented by a script on the ESP32 filesystem ([Files Module](/StarDocs/SysMod/SysModFiles)). Live scripts are pseudo c-code files which are parsed and compiled into assembler and runs at very high speed (like compiled c-code!) without rebooting or flashing!!! Live Fixtures are a specific application of Live Scripts (see [StarBase Live Scripts Module](/StarDocs/UserMod/UserModLiveScripts)).

* A Live Fixture can be executed by selecting an F_ixture.sc file in the [Fixture Module](/StarDocs/StarLightMod/StarLightModFixtures/). 

* Example(s) of Live Effect scripts can be found in [StarLight repo/misc/LiveScripts](https://github.com/MoonModules/StarLight/tree/main/misc/LiveScripts)


Panel example:
```
define horizontalPanels 8
define verticalPanels 6

void main() {
  for (int panelY = 0; panelY < verticalPanels; panelY++) {
    for (int panelX = horizontalPanels-1; panelX >=0; panelX--) {

      for (int x=0; x<16;x++) {
        for (int y=0; y<16; y++) {
          int y2 = y; if (x%2 == 0) {y2=15-y;} //serpentine
          //int panelX2 = panelX + 1; if (panelX2==8) {panelX2 = 0;} //ewowi panel correction
          addPixel(panelX*16+x,panelY*16+y2,0);
        }
      }

    }
  }
}
```

Ring example
```
define PI 3.141592654
define ledCount 100

void main()
{
  setFactor(10); //Coordinates in mm
  setLedSize(2); //smaller leds (default 5)
  for (int radius = 0; radius < 200; radius = radius + 10) {
    for (int i=0; i<radius; i++) {
      int x = radius + sin(i/radius * 2 * PI) * radius;
      int y = radius + cos(i/radius * 2 * PI) * radius;
      addPixel(x/2, y/2, radius);
    }
  }
}
```

Current supported functions are
```
external float atan2(float a1, float a2);
  4 external float hypot(float a1, float a2);
  5 external float sin(float a1);
  6 external float cos(float a1);
  7 external float time(float a1);
  8 external float triangle(float a1);
  9 external uint32_t millis();
 10 external void setFactor(uint8_t a1);
 11 external void setLedSize(uint8_t a1);
 12 external void setShape(uint8_t a1);
 13 external void addPixelsPre();
 14 external void addPixel(uint16_t a1, uint16_t a2, uint16_t a3);
 15 external void addPin(uint8_t a1);
 16 external void addPixelsPost();
```

## Live Fixtures together with Clockless driver

- If both options are available in a build there is also the option to run a mapping projection directly from the F_ixture.sc file.
- Compile with -D STARLIGHT_LIVE_MAPPING option
- WIP
- See [Clockless LED drivers](/StarDocs/StarLight/ClocklessLedDrivers/))

<img width="369" alt="image" src="https://github.com/user-attachments/assets/b8f1178e-bdce-4ef1-af2a-cdbd01ba17c4">


## Live Projections

Not implemented yet
