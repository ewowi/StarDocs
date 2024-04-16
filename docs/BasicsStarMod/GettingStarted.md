---
title: Getting Started
hide:
  # - navigation
  # - toc
---

## Getting Started

* Download a [StarMod binary](https://github.com/ewowi/StarMod/actions) or [StarMod Leds binary](https://github.com/MoonModules/StarModLeds/actions)
    * Click on the latest workflow run, scroll down to Artifacts, then download the bin file
    * Currently only ESP32 builds can be found here. Contact us to provide other builds e.g. c3, S2, S3
* Flash the unzipped "firmware.bin" to an ESP32 module using [ESP Flasher](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_%20ESP_Flasher)
    * Unzip/extract the "firmware.bin" from the downloaded folder, then flash it to your connected ESP32 module

<img width="716" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/c8ab160d-bba0-4d5b-aed4-c858fea3637f">

* Alternatively, you can compile and upload [source code](https://github.com/ewowi/StarMod) via [VSCode](https://code.visualstudio.com) and [PIO](https://platformio.org). 

* The following builds are available using VSCode:

<img width="255" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/cbd75a65-0046-4008-8670-ef97f4393b82">

* Find the "StarMod" WiFi network and connect (no password needed)

<img width="293" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/e7b1e16a-8014-42dc-9e07-f4e0cbf04efd">

* The Captive portal will show the setup tab, alternatively go to [4.3.2.1](http://4.3.2.1)

<img width="896" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/cd8bd820-0a40-4ead-a0d2-14e0d0aa4ac3">

* Give the instance a name
    * [System](/StarDocs/SysMod/SysModSystem)
* Enter your Wifi credentials
    * [Network](/StarDocs/SysMod/SysModNetwork)
    * Note: first Save Model, then connect 
* Save Model
    * [Model](/StarDocs/SysMod/SysModModel)
* Reboot or press Connect
* Connect to the WiFi network
* Optionally choose a Theme
* Setup Application
    * Continue here ! : [Setup StarMod Leds](/StarDocs/BasicsLed/GettingStarted)

## Update StarMod binary

* See Ota Update in [System](/StarDocs/SysMod/SysModSystem)
