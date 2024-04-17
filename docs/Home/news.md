---
title: News
hide:
  - navigation
  - toc
---

## News

### April 6, 2024: StarMod and StarLeds repositories

The LEDs part of [ewowi/StarMod](https://github.com/ewowi/StarMod) has been moved to [MoonModules/StarModLeds](https://github.com/MoonModules/StarModLeds). From now on:

* StarMod is a generic ESP32 platfom without any notion of LEDs
* StarLeds is a fork of StarMod which adds LED functionality on top of it.
* StarMod can be forked by anyone who wants to build an ESP32 application
* Forks of StarMod should not change System functionality, changes on that should be done on StarMod:
    * Sys Modules 
    * Generic User Modules
    * index.js / html / css
    * platformio.ini
* The following should be changed on forks:
    * App Modules
    * main.cpp
    * app.js 
* Use Github issues for [StarMod](https://github.com/ewowi/StarMod/issues) or [StarLeds](https://github.com/MoonModules/StarModLeds/issues) respectively.