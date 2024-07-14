---
title: StarBoard
hide:
  # - navigation
  # - toc
---

## StarBoard

Here are some ideas for the perfect board to drive LEDs. 
Most likely there are more perfect boards, so they can be added here.

## StarBoardLeds

Mockup:

<img width="400" src="https://github.com/ewowi/StarDocs/assets/138451817/2990689a-cf37-4da7-9a60-4973d16ef74f">

* USB-C Powered (2.5A)
* ESP32-S3 based
* Headers to plugin INMP443 (no onboard mic as we got non functioning mics at  JLCPCB once probably due to wrong hole alignment or too much paste)
* 5 input/outputs with standard leds pin headers (Red, Green, White = +,data,- per default)
* Level shifters with solder pads to enable them per input/output
* 5 input/outputs can be used to drive leds or repurposed for other io
* all on one board
* perfect for: plug and play development boards, fairy lights (HSC), 256-400 leds per pin at reduced brightness, 50-125 leds at full brightness
* optional: separate screw terminal to 5V power the board and the 5 io headers with more than 2.5A
    * optional: allow higher voltages for >5V led strips/panels
* optional: i2s, one or two in parallel for gyro board and or 4 line display
* plus printable enclosure

    * inspiration
    * <img width="400" src="https://github.com/ewowi/StarDocs/assets/138451817/cc491eee-fed6-421d-a438-20da375b3ba2">
    * On/Off button
    * Optional: mode button (next effect, next preset, ...)
    * Optional: brightness knob

## StarBoard More

* Higher power (1024 leds, 20-50mA each => 20-50A)
* Line in
* Ethernet
* Display (touch?)
* external antenna
* lipo charge
* ir
* dallas temp
* 18650 or 26650 battery holder
