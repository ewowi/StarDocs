---
title: Getting Started
hide:
  # - navigation
  # - toc
---

## Follow these steps to get StarBase or StarLight running

**1. Acquire a firmware binary (bin)**

Use a pre-built bin (Beginner-Advanced)
		
* [StarBase release](https://github.com/ewowi/StarBase/releases) or [StarLight release](https://github.com/MoonModules/StarLight/releases)
* [StarBase latest](https://github.com/ewowi/StarBase/actions) or [StarLight latest](https://github.com/MoonModules/StarLight/actions)
* Click on the latest workflow run, scroll down to Artifacts, then download the bin file
		* Currently only esp32dev builds can be found here

Build your own bin (Intermediate-Advanced)

  * Compile a bin using [StarBase source code](https://github.com/ewowi/StarBase) or [StarLight source code](https://github.com/MoonModules/StarLight) via [VSCode](https://code.visualstudio.com) and [PIO](https://platformio.org). 
        * The following builds are available using VSCode:
          
	<img width="255" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/cbd75a65-0046-4008-8670-ef97f4393b82">

**2. Flash StarMod an ESP32 board**

* Flash the unzipped "firmware.bin" to an ESP32 module using [ESP Flasher](https://github.com/srg74/WLED-wemos-shield/tree/master/resources/Firmware/WLED_%20ESP_Flasher)
* Unzip/extract the "firmware.bin" from the downloaded folder, then flash it to your connected ESP32 module
      
	<img width="450" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/c8ab160d-bba0-4d5b-aed4-c858fea3637f">

**3. Set up the StarMod instance**
    
* Find the "StarBase" WiFi network broadcasted by the ESP32 and connect (no password needed)

	<img width="293" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/e7b1e16a-8014-42dc-9e07-f4e0cbf04efd">

* The StarMod adaptive portal will show the setup tab. Alternatively, go to [4.3.2.1](http://4.3.2.1)
  
        <img width="450" alt="image" src="https://github.com/user-attachments/assets/040584d6-dc81-43f5-bf9b-f476ab64d6c0">

* Give the instance a name
	* Read more: [System](/StarDocs/SysMod/SysModSystem)
  
* Enter your Wifi credentials
  * Read more: [Network](/StarDocs/SysMod/SysModNetwork)
* Save Model to preserve credentials after reboot
  * Read more: [Model](/StarDocs/SysMod/SysModModel)

**4. Start using Starmod**
  * Connect to the WiFi network
  * [Configure StarLight](/StarDocs/StarLight/GettingStarted)

## Updating the StarBase binary

* See Ota Update in [System](/StarDocs/SysMod/SysModSystem)
