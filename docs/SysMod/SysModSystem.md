---
title: System Module
hide:
  # - navigation
  # - toc
---


<video width="248" autoplay><source src="https://github.com/ewowi/StarDocs/assets/1737159/212f8043-cf2c-480a-bae9-96c16674b412" type="video/mp4"></video>

## System

* Name: name of this instance, default StarMod. Will be used as hostname, AP name etc.
* Reboot: restart this instance.
* OTA Update: select a bin file and it will directly upload to the board. Red or green ball will show failure or success. Update will be effective after reboot !!

## Curl update / upload

Alternetively to OTA Update in the UI, New versions of StarMod can be flashed to an already flashed esp32 using:

```
curl -s -F "update=@<path/firmware.bin>" <ip>/update
```

* replace ```<path/firmware.bin>``` and ```<ip>``` with the relevant values.
* above command will report if the update was succesful
* After sucessful update you need to reboot the device to make the update effective


🚧
