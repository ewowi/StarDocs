---
title: StarBoard
hide:
  # - navigation
  # - toc
---

## StarBoard

Here are some ideas for the perfect board for StarMod. 
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
* optional: separate screw terminal to power the board and the 5 io headers wirh more than 2.5A

## StarBoard More

* Higher power (1024 leds, 20-50mA each => 20-50A)
* Line in
* Ethernet
* Display (touch?)
