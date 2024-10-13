---
title: User Mod Live Scripts
hide:
  # - navigation
  # - toc
---

## Introduction

* Live scripts are pseudo c-code files which are parsed and compiled into assembler and runs at high speed without rebooting or flashing. They can be used by end-user of StarBase (or one if its forks) to create custom code without talking to StarBase developers asking to publish a new version with the new code in it.
Live scripts are implemented using [hpwit/ESPLiveScript](https://github.com/hpwit/ESPLiveScript/tree/v2.8). Both this repo and the implementation in StarMod is in development and more and more functionality is expected to be released.
Live scripts are stored on the filesystem and can be uploaded, edited and deleted in the [Files Module](/StarDocs/SysMod/SysModFiles), the have extension .sc.
Example(s) of scripts can be found in [StarBase repo/misc/LiveScripts](https://github.com/ewowi/StarBase/tree/main/misc/LiveScripts)

The most basic program is blink.sc: 

```
define OUTPUT            0x03 
define LOW               0x0
define HIGH              0x1

uint8_t blinkPin;

void setup()
{
  blinkPin = 5;
  pinMode(blinkPin, OUTPUT);
}

void loop() {
    digitalWrite(blinkPin, HIGH);  // turn the LED on (HIGH is the voltage level)
    delay(1000);                      // wait for a second
    digitalWrite(blinkPin, LOW);   // turn the LED off by making the voltage LOW
    delay(1000);                      // wait for a second
}
```

pinMode, digitalWrite and delay are 'externally' defined functions, in other words, StarBase have implemented them. Currently this are even the only defined functions, so this will be expanded in furter developing Live Scrips, which in turn is triggered by user needs, these can be reported in [Github issues](https://github.com/ewowi/StarBase/issues).

## Preparing  live scripts
* Make sure StarBase is compiled with compiler directive STARBASE_USERMOD_LIVE set (this is default)
* Make sure Live Scripts is enabled in the [Modules Module](/StarDocs/SysMod/SysModModules) (this is not default)

## Running a live script

* First upload a script from your file system to the [Files Module](/StarDocs/SysMod/SysModFiles)
* Navigate to the Live Scripts module and select a script in the drop down module
* A script can be edited in the [Files Module](/StarDocs/SysMod/SysModFiles), if you save a currently running script, it will automatically be recompiled and reran.
* To make the blink example work for the pin of the on-board LED, change the blinkPin assignment in above script
* To see that the scripts work, change the delay and see the result on your on-board LED.