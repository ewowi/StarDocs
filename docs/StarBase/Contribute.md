---
title: Contribute
hide:
  # - navigation
  # - toc
---

## Contribute

If you want to help with StarMod, the following items could use helping hands:

StarBase:

* Custom bin name - Small, see also [issues/48](https://github.com/ewowi/StarBase/issues/48) 🚧
* Improve UI - Big, see [issues/54](https://github.com/ewowi/StarBase/issues/54)
* Setup StarMod.org (StarBase.org?) - Medium
* Print to different targets (Serial, file, net) - Medium 🚧
* Promote StarBase to other communities eg Fastled community
* Improve pins viewer, see [gpio viewer](https://github.com/thelastoutpostworkshop/gpio_viewer/issues/110) - Big 🚧
* Example AppModules (eg FastLed, blink, pin high/low, gyro viewer, ...) see [issues/50](https://github.com/ewowi/StarBase/issues/50)
* StarLink: synchronized time within 20ms between instances (look for Toki::Time and timebase) - @ewowi 🚧
* replace ESPAsyncWebServer by the new one wled uses (get rid of occassionaly assert failed: multi_heap_free multi_heap_poisoning.c:259 (head != NULL) when on usb/pio)
* Presets: a module can store it's current values to file system and if there are more you can select one of them
* DMX / Artnet 🚧
* Home Assistant 🚧
* Basic devices (I2S support (e.g. gyro, buttons, rotary encoder), support for on/off and brightness hardware
* ...

StarLight

* Create new effects - Medium
    * @WildCats Game of Life on 2D and 3D 🚧
    * Analog VU meter
    * Akemi like effect for StarLight - need to design a StarMod avatar
    * Create a universal fire effect, suitable for 1D, 2D and 3D. See also [StarLight Effects](https://ewowi.github.io/StarDocs/StarLight/Effects/) on effect and projection dimensions 
* Create new projections - Medium
    * revisit the projection mechanism: @ewowi, planned in July, WildCats08
    * See [theory](https://ewowi.github.io/StarDocs/StarLight/ProjectionsAndMappings/#more-theory)
* Fixture generator preview - Medium
* Generate your fixture - Medium
    * [burning man](https://3dwarehouse.sketchup.com/model/e9de47b1-02f6-4677-a2ad-e73c1af6442f/Burning-Man-Effigy) - create conversion script between 3D models and StarLight 
    * bike fixture - ewowi (the bike is ready: [insta](https://www.instagram.com/reel/C7zkuuYuvhC/?igsh=MWZkYXJheXZqc3FzYw==) )
* Sound reactive palette
* New bin -> default fixture and default effect
* Sound reactive (now sound sync)
* use Fusion (or other CAD tool) to generate F_ixture.json files, optionally draw lamps with lights and extract the json from it (possibly with python api?) 

Both

* Documention (this):
    * @MONSOONO / @Flavourdynamics 🚧

Contact us on [Discord](https://discord.gg/VGDGGX8qvQ).
