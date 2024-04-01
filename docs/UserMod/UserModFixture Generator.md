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
    * IP: will be used for super-sync (Not implemented yet)
    * pin: the pin this fixture is connected to
    * custom parameters like number of leds, coordinates
 * A fixture can be made out of multiple panels. Panels can be matrices but also rings etc. If the panel checkbox is checked, each panel can be specified in a table
 * If Panel is selected, presets can be selected, e.g. for fixture Matrix, 16x16, 4*16x16, cube etc can be selected
 * In the panel table, each panel can be give a seperate (or same) pin
 * After pressing generate, a fixture file will be generated, see [Files](/StarDocs/SysMod/SysModFiles) and can be selected, see [Fixtures](/StarDocs/LedMod/LedModFixture)

### Matrix fixtures

<img width="361" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/1f276d52-f19a-45a7-93a9-854214af9a99">

For each panel:

* First Led: the position of the first led
* Row End: the position of the last led in the first row
* Column End: The position of the last column of the panel.
    * Odd nr of columns: if the column end matches the First led then the leds are layed out in serpentine 
    * Even nr of columns: if the column end matches the Row End then the leds are layed out in serpentine 

<img width="326" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/2288dfa6-e063-4d8e-88c6-9bd53c196b12">

## Examples

<img width="316" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/d48679eb-efbe-4133-b43d-e3f33587530a">
<img width="336" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/58530e7d-0606-4928-a4ae-233103f88e34">
<img width="340" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/62073790-5365-4cee-be0e-78488d285b2a">
<img width="329" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/b6909720-4a8e-4661-9381-4336aeed1283">
<img width="317" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/4a343d06-8fa3-4ea6-a521-0cc9e5d2bfb2">

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
* Files need to have a name starting with F_ and extension.json
* Files can be uploaded to the esp32 board in the [Files](/StarDocs/SysMod/SysModFiles) or using the command ```curl -F 'data=@<FileName>' <ip>/upload``` where ```<FileName>``` and ```<ip>``` must be replaced by relevant values
