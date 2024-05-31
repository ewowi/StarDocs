---
title: Getting Started
hide:
  # - navigation
  # - toc
---

## Getting Started

* Download a firmware binary (bin)
    * [StarBase release](https://github.com/ewowi/StarBase/releases) or [StarLeds release](https://github.com/MoonModules/StarLeds/releases)
    * [StarBase latest](https://github.com/ewowi/StarBase/actions) or [StarLeds latest](https://github.com/MoonModules/StarLeds/actions)
        * Click on the latest workflow run, scroll down to Artifacts, then download the bin file
        * Currently only esp32dev builds can be found here
    * Compile a bin using [StarBase source code](https://github.com/ewowi/StarBase) or [StarLeds source code](https://github.com/MoonModules/StarLeds) via [VSCode](https://code.visualstudio.com) and [PIO](https://platformio.org). 
        * The following builds are available using VSCode:

        <img width="255" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/cbd75a65-0046-4008-8670-ef97f4393b82">

* Flash the unzipped "firmware.bin" to an ESP32 module using [ESP Flasher](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_%20ESP_Flasher)
    * Unzip/extract the "firmware.bin" from the downloaded folder, then flash it to your connected ESP32 module

<img width="716" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/c8ab160d-bba0-4d5b-aed4-c858fea3637f">

* Find the "StarBase" WiFi network and connect (no password needed)

<img width="293" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/e7b1e16a-8014-42dc-9e07-f4e0cbf04efd">

* The StarMod adaptive portal will show the setup tab, alternatively go to [4.3.2.1](http://4.3.2.1)

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
* Optionally, choose a display theme
* Setup the application
    * Continue here ! : [Setup StarLeds](/StarDocs/StarLeds/GettingStarted)

## Update StarBase binary

* See Ota Update in [System](/StarDocs/SysMod/SysModSystem)
