---
title: News
hide:
  # - navigation
  # - toc
---

## News

### April 17, 2024: New test scenario: OTA Update

see [StarBase Testing](https://ewowi.github.io/StarDocs/StarBase/Testing/)

<img width="400" alt="Screenshot 2024-04-17 at 10 52 13" src="https://github.com/ewowi/StarDocs/assets/138451817/fc72063e-20b5-4f55-ba13-cbe80b889b0b">

* Testers wanted to test OTA update, and also Getting Started 
* Can be tested on StarBase or StarLeds, StarLeds is the most feature rich test
* Release 0.0.0 has been added in github repos of StarBase and StarLeds you can download bins there
* Different target boards supported, esp32, esp32s3, esp32s2, esp32c3, pico32
* Some work has been done on documentation in StarDocs but still far from complete and sometimes in telegram style. Improving the docs by forking and submitting pull requests is highly appreciated :wink:
* Check also the [contribute page](https://ewowi.github.io/StarDocs/StarBase/Contribute/)



### April 6, 2024: StarBase and StarLeds repositories

The LEDs part of [ewowi/StarBase](https://github.com/ewowi/StarBase) has been moved to [MoonModules/StarLeds](https://github.com/MoonModules/StarLeds). From now on:

* StarBase is a generic ESP32 platfom without any notion of LEDs
* StarLeds is a fork of StarBase which adds LED functionality on top of it.
* StarBase can be forked by anyone who wants to build an ESP32 application
* Forks of StarBase should not change System functionality, changes on that should be done on StarBase:
    * Sys Modules 
    * Generic User Modules
    * index.js / html / css
    * platformio.ini
* The following should be changed on forks:
    * App Modules
    * main.cpp
    * app.js 
* Use Github issues for [StarBase](https://github.com/ewowi/StarBase/issues) or [StarLeds](https://github.com/MoonModules/StarLeds/issues) respectively.
