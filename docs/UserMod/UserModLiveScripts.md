---
title: UserMod Live Scripts
hide:
  # - navigation
  # - toc
---

<img width="450" alt="image" src="https://github.com/user-attachments/assets/9d26c8d3-edbd-44d2-b3a2-26c7ff5ce579">

## Introduction

Live scripts are pseudo c-code files which are parsed and compiled into assembler and runs at very high speed (like compiled c-code!) without rebooting or flashing!!! They can be used by end-users of StarBase (or one if its forks) to create custom code without the need to publish a new version with the new code in it.
You might need to read above section again, as this is mindblowing functionality! 🙂

Live scripts are implemented using [hpwit/ESPLiveScript](https://github.com/hpwit/ESPLiveScript/tree/v2.8). Both this repo and the implementation in StarBase is in development and more functionality is expected to be released.

Live scripts are stored on the filesystem and can be uploaded, edited and deleted in the [Files Module](/StarDocs/SysMod/SysModFiles), they have extension .sc.

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

pinMode, digitalWrite and delay are 'externally' defined functions, in other words, StarBase have implemented them. Currently these are the only defined functions and more functions will be available later, requests for new functions can be requested in [Github issues](https://github.com/ewowi/StarBase/issues).

Applications of Live Scripts can be 'anything' but low hanging fruit is making controllers which read data from pins connected to sensors do some processing and then write data to pins connected to motors, lights etc

Note: StarLight uses Live Scripts to implement [Live Effects](/StarDocs/StarLight/LiveEffects/) (since Release 0.3.0) and Live Fixtures (Planned for Release 0.5.0).

## Supported StarBase functions to be used in scrips

    addExternalFun("void", "show", "()", (void *)&show); //comment if setup/loop model works
    addExternalFun("void", "resetStat", "()", (void *)&resetShowStats);

    addExternalFun("void", "display", "(int a1)", (void *)&dispshit);
    addExternalFun("void", "dp", "(float a1)", (void *)displayfloat);
    addExternalFun("void", "error", "(int a1, int a2, int a3)", (void *)&showError);
    addExternalFun("void", "print", "(char * a1)", (void *)__print);

    addExternalFun("float", "atan2","(float a1, float a2)",(void*)_atan2);
    addExternalFun("float", "hypot","(float a1, float a2)",(void*)_hypot);
    addExternalFun("float", "sin", "(float a1)", (void *)_sin);
    addExternalFun("float", "time", "(float a1)", (void *)_time);
    addExternalFun("float", "triangle", "(float a1)", (void *)_triangle);
    addExternalFun("uint32_t", "millis", "()", (void *)millis);

    // added by StarBase
    addExternalFun("void", "pinMode", "(int a1, int a2)", (void *)&pinMode);
    addExternalFun("void", "digitalWrite", "(int a1, int a2)", (void *)&digitalWrite);
    addExternalFun("void", "delay", "(int a1)", (void *)&delay);

## Preparing  live scripts
* StarBase most be compiled with compiler directive STARBASE_USERMOD_LIVE set (this is default)
* Live Scripts must be enabled in the [Modules Module](/StarDocs/SysMod/SysModModules) (this is not default)

## Running a live script

* First upload a script from your file system to the [Files Module](/StarDocs/SysMod/SysModFiles)
* Navigate to the Live Scripts module and select a script in the drop down module
* A script can be edited in the [Files Module](/StarDocs/SysMod/SysModFiles), if you save a currently running script, it will automatically be recompiled and reran.
* To make the blink example work for the pin of the on-board LED, change the blinkPin assignment in above script
* To see that the scripts work, edit, change the delay, save and see the result on your on-board LED.
* Monitoring execution of Live Scripts is work in progress, you can check serial output, or redirect output to UI in the [Print Module](/StarDocs/SysMod/SysModPrint)
