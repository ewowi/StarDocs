---
title: Live Effects
hide:
  # - navigation
  # - toc
---

<img width="450" alt="image" src="https://github.com/user-attachments/assets/418fb6ee-3580-456e-97e0-9344a0d13fac">

## Introduction

Live Effects are effects implemented by a script on the ESP32 filesystem ([Files Module](/StarDocs/SysMod/SysModFiles)), instead of precompiled in a StarLight binary flash file. Live effects are a specific application of Live Scripts (see [Live Scripts Module](/StarDocs/UserMod/UserModLiveScripts)).

* A Life Effect can be executed by selecting Live Effect in the [Effects Module](/StarDocs/StarLightMod/StarLightModEffects/). (Currently only one Live Effect can run, more in Release 0.5.0).

* Next a script can be selected with the .sc file extension. After selection the file will be executed directly:

    <img width="362" alt="image" src="https://github.com/user-attachments/assets/de946239-6ad7-4df5-bbd1-92e484be57f0">

* Optionally Slider1, 2, or 3 controls can be used to change the behaviour of the effect (in future release slider types and names can be defined in the life script itself).

* Example(s) of Life Effect scripts can be found in [StarLight repo/misc/LiveScripts](https://github.com/MoonModules/StarLight/tree/main/misc/LiveScripts)

## StarLight Live functions
Supported StarLight functions to be used in scrips

* ```CRGB    hsv(uint8_t hue, uint8_t saturation, uint8_t value)```: HSV Color
* ```CRGB    rgb (uint8_t red, uint8_t green, uint8_t blue)```: RGB color
* ```uint8_t beatSin8 (uint8_t bpm, uint8_t lowest, uint8_t highest)``` Beats per minute 
* ```uint8_t inoise8 (uint16_t x, uint16_t y, uint16_t z)``` xyz coordinate on noise map (3D)
* ```uint8_t random8()```: random between 0 and 255
* ```uint8_t sin8(uint8_t theta)```: theta input angle from 0-255, results 0-255
* ```uint8_t cos8(uint8_t theta)```: theta input angle from 0-255, results 0-255
* ```void    sPC(uint16_t pixel, CRGB color)```: setPixelColor: 
* ```void    sCFP(uint16_t pixel, uint8_t color index, uint8_t brightness)```: Set Color From Palette
* ```void    fadeToBlackBy(uint8_t fadeBy)```

* plus [StarBase Live functions](/StarDocs/UserMod/UserModLiveScripts/#starbase-live-functions)

## Preparing and running Live Effects

* See [Preparing live scripts](StarDocs/UserMod/UserModLiveScripts/#preparing-live-scripts) and [Running live scripts](/StarDocs/UserMod/UserModLiveScripts/#running-live-scripts)
