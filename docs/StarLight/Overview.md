---
title: StarLight Overview
hide:
  # - navigation
  # - toc
---

StarLight is the fork of StarMod designed to control LEDs.

StarLight relies on defing a ([fixture](StarDocs/StarLightMod/StarLightModFixtureGenerator/)), which is a map between your physical LEDs and their virtual representation. This allows the user to run ([Effects](StarDocs/StarLightMod/StarLightModEffects/)), with a selected Projection, which modifies how the Effect is displayed.

All StarLight modules support 1D, 2D, 3D effects and fixtures. Effects operate independently of fixtures it is displayed on (e.g. a 1D effect can be projected on a 3D fixture or a 3D effect on a 1D fixture (strip))

Fixture generator:

<img width="481" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/06cc1d89-ce54-4feb-8023-581bfce16fbd">

Effects:

<img width="486" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/7a4637e5-383a-4935-8057-9cd7ba64b427">

Fixture:

<img width="390" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/59dc199c-6697-43f4-9a1b-f8413005aa5f">

## Mappings

In the world of LED software, "mapping" is a word that causeses a lot of discussion and confusion. StarLight is designed to make it simpler and more flexible, by having a clear separation of physical "mapping" and logical "mapping", with a clear distinction of fixtures, effects and projections (see [Orthogonality](StarDocs/StarBase/StandardsAndGuidelines/)). This is explained further below (please consider contributing to this description with pictures and clarifications):

* F_ixture.json contains a definition of the fixture. It specifies the name, nrOfLeds and the width, height and depth of the fixture in cm. Note that nrOfLeds is not equal to the product of width, height and depth as in a lot of fixtures there is not a pixel on every cm. Panels and strips do have a pixel on each cm but rings or hexagons or wheels etc not. Furthermore it specifies for each pin (or ip addres - WIP) the physical coordinate of the pixels (in mm as circular fixtures requires mm accuracy !!) which are connected to the pin, in order of pixels connected in the daisy chain.
* An effect specifies in a virtual width, height and depth what the effect does. It uses a FASTLED compatible syntax including leds[i] assignments. Also setPixelColor and getPixelColor can be used. Effect can be 1D, 2D or 3D.
* A projection maps the virtual effect to the physical fixture. The Default projection maps the effect width, height and depth to the fixture width, height and depth. E.g. if a 2D effect is mapped to a matrix there will be a 1:1 correspondence. If a 2D effect is mapped to a 3D fixture (e.g. humanSizedCube) it will smear the 2D image over 3D. Other projections can multiply effects, rotate effects etc. Projections are still in its infancy and only some basic projections have been defined.

## Dev

* Fixtures are generated in StarLightModFixtureGen.h
* Effects are defined in LedEffects.h
* Projections are defined in LedFixture.cpp
* Fixtures are controlled in StarLightModFixture.h
* StarLightModEffects.h glues all of this together: one or more effects each with their own projections and locations on the fixture are called in the main loop and send to FastLed (FastLED.show()). If fixture, dimensions or projections change, fixture.projectAndMap is called to create new mappings. For each new fixture the pins defined in the fixture are allocated (FastLED.addLeds)

_Starlight, starbright
First star I see tonight
Starlight (Starbright)
Make everything all right
Starlight, starbright
First star I see tonight
Starlight (Starbright), yeah
You must be my Lucky Star_

---- By Madonna
