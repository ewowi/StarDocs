---
title: Getting Started
hide:
  # - navigation
  # - toc
---

![image](https://github.com/ewowi/StarDocs/assets/1737159/1971587b-372f-4427-8600-92f9071ba82d)

## Getting Started

* Download a StarMod Binary

* Flash it to an ESP32 module

* Connect leds to the ESP32 module

* Find StarMod AP network and connect

* Go to 4.3.2.1

* Give the instance a name
    * [System](/StarDocs/SysMod/SysModSystem)

* Enter your Wifi cridentials
    * [Network](/StarDocs/SysMod/SysModNetwork)

* Save Model
    * [Model](/StarDocs/SysMod/SysModModel)

* Setup Application
    * [Setup Leds](/StarDocs/LedMod/GettingStarted)

## Updating

New versions of StarMod can be flashed to an already flashed esp32 using:

```
curl -s -F "update=@<path/firmware.bin>" <ip>/update
```

replace ```<path/firmware.bin>``` and ```<ip>``` with the relevant values.

