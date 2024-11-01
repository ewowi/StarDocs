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

If you run StarLight, read more about Live Effects, Live Fixtures and Live Projections [here](/StarDocs/StarLight/LiveScripts).

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

Applications of Live Scripts can be 'anything' but low hanging fruit is making controllers which read data from pins connected to sensors do some processing and then write data to pins connected to motors, lights etc

Note: StarLight uses Live Scripts to implement [StarLight Live Effects](/StarDocs/StarLight/LiveEffects/) (since Release 0.3.0) and Live Fixtures (Planned for Release 0.5.0).

## StarBase Live functions
Supported StarBase functions to be used in scrips

    void show (); //Called automatically. calls driver.show() + statistics
    void resetStat (); // Called automatically

    void display (int a1)
    void dp (float a1); //display float, for debugging
    void error (int a1, int a2, int a3); //prints 3 integers
    void print (char * a1); //prints one string

    float atan2 (float a1, float a2)
    float hypot (float a1, float a2)
    float sin (float a1)
    float time (float a1); //A sawtooth waveform between 0.0 and 1.0 that loops about every 65.536*interval seconds. e.g. use .015 for an approximately 1 second.
    float triangle (float a1); //Converts a sawtooth waveform v between 0.0 and 1.0 to a triangle waveform between 0.0 to 1.0. v "wraps" between 0.0 and 1.0.
    wave //not implemented yet ...Converts a sawtooth waveform v between 0.0 and 1.0 to a sinusoidal waveform between 0.0 to 1.0. Same as (1+sin(v*PI2))/2 but faster. v "wraps" between 0.0 and 1.0.
    square // not implemented yet ...Converts a sawtooth waveform v to a square wave using the provided duty cycle where duty is a number between 0.0 and 1.0. v "wraps" between 0.0 and 1.0.
    clamp // not implemented yet ... see also https://github.com/atuline/PixelBlaze
    uint32_t millis ()

    void pinMode (int a1, int a2)
    void digitalWrite (int a1, int a2)
    void delay (int a1)

* more functions will be available later, new functions can be requested in [Github issues](https://github.com/ewowi/StarBase/issues).

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
