---
title: LedModEffects
hide:
  # - navigation
  # - toc
---

<img width="486" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/1b6b6f51-5a3a-4044-af58-70780f731863">

One or more effects can be defined. Currently there are some works in progress

* If adding more then one effect Start and End is not set with defaults, resulting in a crash. Workaround is to set them manually first before selecting the effect
* If there is more then one effect, deleting effects should be from last to first, otherwise unexpected behavior.

## List of effects

This list is not complete 🚧

* Rubik's Cube Effect
    * Simulates cube sizes from 2x2 to 8x8 on 3D fixtures.
    * Demonstrates solving by reversing the initial scramble.
    * Option for infinite random turns.

* Game of Life Options
    * Infinite Mode: Continuously spawns random cells, preventing the game from ending or repeating.
    * Color By Age: Cells spawn green and gradually fade to red as they age.
 
* Praxis Effect
    * This effect has a large range of adjustability based on two oscillating functions: the Macro Mutator and the Micro Mutator.
    * Each mutator can be adjusted, with the ability to change the frequency and range of each oscillation. Faster frequency and greater ranges will result in a more frantic effect, whereas smaller frequencies and ranges will result in a more relaxed effect.
    * Try looking at wide range for either mutator, while setting the frequency on the other mutator to 0. Start with a low frequency to identify a range that you prefer, then try adding in the other mutator.

* 1D Effect Rainbow
    * Features speed and scale sliders.

* 1D Effect Flow
    * Features speed and scale sliders.

* Live Script Effect
    * see [Live Script Effects Module](/StarDocs/StarLight/LiveScriptsEffects)



## Effects

<img width="154" alt="image" src="https://github.com/ewowi/StarDocs/assets/1737159/a7a582f8-ba4d-48af-b01b-4cd03a21befd">

An effect has multiple tags, tags are shown in the drop down. Any tag is possible, not necessarily limited to 1D, 2D, sound, etc

Current tags

┊1D

▦ 2D

🧊3D

♪ Audio Volume 

♫ Audio Frequency

💫StarLight origin

⚡FastLed origin

💡WLED origin

💡💫 WLED origin, StarLight enhanced

### Dev

### See also

* [Effects](/StarDocs/StarLight/Effects)

* [Projections And Mappings](/StarDocs/StarLight/ProjectionsAndMappings) : virtual to physical mapping of an effect
