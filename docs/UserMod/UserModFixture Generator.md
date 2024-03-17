---
title: UserMod Fixture Generator
hide:
  # - navigation
  # - toc
---

<img width="526" alt="image" src="https://github.com/ewowi/StarDocs/assets/1737159/82fff9b5-2459-4706-9f5b-7125e4bc7717">

## Fixture Generator

Fixtures can be generated (predefined) or manually created, see below.

The fixture generator generates predefined fixtures, specific parameters can be added e.g. size of panels etc:

<img width="129" alt="image" src="https://github.com/ewowi/StarDocs/assets/1737159/d7b89a67-2c2c-449f-86ca-c4f5b4a54c5d">

* Fixture: matrix, panels rings etc.
* For each fixture:
    * IP: will be used for super-sync (WIP)
    * pin: the pin this fixture is connected to
    * custom parameters like number of leds, coordinates
 * A fixture can be made out of multiple panels. Panels can be matrices but also rings etc. If the panel checkbox is checked, each panel can be specified in a table
 * If Panel is selected, presets can be selected, e.g. for fixture Matrix, 16x16, 4*16x16, cube etc can be selected
 * In the panel table, each panel can be give a seperate (or same) pin
 * After pressing generate, a fixture file will be generated, see [Files](/StarDocs/SysMod/SysModFiles) and can be selected, see [Fixtures](/StarDocs/LedMod/LedModFixture)

## Manually creating a fixture file

```
{"name":"F_4x16x16","nrOfLeds":1024,"width":32,"height":32,"depth":1,"outputs":
      [{"pin":2,"leds":[[0,0,0],[0,10,0] ...[310,150,0]]},
       {"pin":2,"leds":[[0,160,0],[0,170,0] ...[310,310,0]]}]
}
```

* nrOfLeds, the total number of physical leds
* width, heigth, depth: the physical size of the fixture, in cm ! (note width*height*depth is not necessary equal to nr of leds)
* outputs: multuple lists of pin and a nr of leds, for each led, the coordinate in mm !
