---
title: Clockless Led Drivers
hide:
  # - navigation
  # - toc
---

## Introduction

StarLight uses FastLED as the default driver of LEDs, FastLED is not flexible in (re)assigning pins, they need to be defined during compile time. In StarLight a workaround has been made to precompile all templates for possible pins for a specific board so you reassign by choosing another pin and another precompiled template will be used (or multiple in case you drive multiple pins). Each pin template is around 700 bytes (check) so this creates an overhead in flash / memory.

## I2S Clockless Led Driver

Alternatively you can choose for [I2SClocklessLedDriver](https://github.com/hpwit/I2SClocklessLedDriver) if you are compiling from VSCode by uncommenting this in platformio.ini (contact us if you need a precompiled binary).

Uncomment the 2 lines for build flags and lib deps to choose on of the alternatives for the FastLED driver:

<img width="420" alt="image" src="https://github.com/user-attachments/assets/041713aa-1b21-4d1b-a9b0-391522f61454">

This has the following advantages

- See above 
- I2S ... 
- Clockless ...
- [I2SClockLessLedDriveresp32s3](https://github.com/hpwit/I2SClockLessLedDriveresp32s3) supports S3 boards. Status ...

For more info check the readme in the link above

## I2S Virtual Clockless Led Driver

If you want to build bigger LED setups at a reasonable frame rate the pins an ESP32 board provides are not enough. [I2SClocklessVirtualLedDriver](https://github.com/hpwit/I2SClocklessVirtualLedDriver) solves this by using I2S to send LED data to one or more SN495 shift registers ic's where each ic sends LEDS data to 8 pins. For instance, if you have 6 ic's you can drive 48 panels of size 16x16 at their max speed which is 120-130fps. This is a total of 12288 LEDs. The ESP32 is powerfull enough to run most effects with this size at speeds ranging from 60-120fps depending on the complexity of the effect.

For more info check the readme in the link above.

Example of a board with 6 SN495 shift registers (and one 245 array to distribute to the shift registers)

<img width="450" alt="image" src="https://github.com/user-attachments/assets/b4a34ce0-4a7c-4adc-8cab-9337287ce39c">

* The shift registers also act as level shifter providing 5 volts to the LED data pins.
* Virtual driver on S3 not yet supported ...
* A design for a 15 panel set up is in progress:


<img width="450" alt="image" src="https://github.com/user-attachments/assets/71b614f9-aad6-4dfa-b664-cc9228a8f59b">


## Notes
* The clockless LED drivers work totally independently from Live Scripts functionality, so you can run live effects with the FastLED driver and run normal effects using one of Clockless drivers.
* IN the Fixture module, you can see which driver is used (FastLED show, CLD show or CLVD show)

<img width="221" alt="image" src="https://github.com/user-attachments/assets/ff42bf99-935e-47d4-834e-129ba3129859">
