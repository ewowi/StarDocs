---
title: Getting Started
hide:
  # - navigation
  # - toc
---

![image](https://github.com/ewowi/StarDocs/assets/1737159/1971587b-372f-4427-8600-92f9071ba82d)

## Getting Started

At the moment of writing some functionality still 🚧 (Installer, Captive portal, OTA flash in UI). Manual steps are provided here.

* Download a StarMod Binary

* Flash it to an ESP32 module
    * Compile and upload [source code](https://github.com/ewowi/StarMod) via [VSCcode](https://code.visualstudio.com) / [PIO](https://platformio.org)
    * Flash a [binary](https://github.com/ewowi/StarMod/actions) (Click on a workflow run, scroll down to Artifacts, download the bin) using [ESP Flasher](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_%20ESP_Flasher)

* Find StarMod AP network and connect using password star1234

* Go to 4.3.2.1

* Give the instance a name
    * [System](/StarDocs/SysMod/SysModSystem)

* Enter your Wifi credentials
    * [Network](/StarDocs/SysMod/SysModNetwork)
    * Note: first Save Model, then connect 

* Save Model
    * [Model](/StarDocs/SysMod/SysModModel)

* Reboot or press Connect

* Setup Application
    * [Setup Leds](/StarDocs/LedMod/GettingStarted)

## Update StarMod binary

* See Ota Update in [System](/StarDocs/SysMod/SysModSystem)
