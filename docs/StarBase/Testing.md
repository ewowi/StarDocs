---
title: Testing
hide:
  # - navigation
  # - toc
---

## Testing StarBase

[StarBase](/StarDocs) is in user test phase. Test scenarios are currently developed. See below for current available test scenarios. If you want to participate in testing:

* Follow a test scenario
* Please report issues in [Github StarBase issues](https://github.com/ewowi/StarBase/issues) or [Github StarLeds issues](https://github.com/MoonModules/StarLeds/issues)
    * Include the build you are testing (see [System](/StarDocs/SysMod/SysModSystem))
    * Include the test scenario
* You can report success also in Github issues or on [Discord / StarMod](https://discord.gg/VGDGGX8qvQ) and include things not clear, suggestions for improvement, new test scenarios etc.
* Improve this documentation by forking [StarDocs](https://github.com/ewowi/StarDocs), edit and submit a pull request
* Any feedback big or small is welcome
* See [StarBase 💫.pdf](https://github.com/ewowi/StarDocs/files/14837446/Starmod.pdf) for the story of StarBase in bullet points

## Current test scenarios

* [Getting Started](/StarDocs/StarBase/GettingStarted/)
    * Follow the instructions until StarLeds is up and running
    * Optionally add a led panel or ring to a gpio port of the esp32 and check leds are burning
* [OTA Update](/StarDocs/SysMod/SysModSystem/)
    * Download a firmware bin, see [Getting Started](/StarDocs/StarBase/GettingStarted/)
    * in the [System module](/StarDocs/SysMod/SysModSystem):
        * Check the currently installed build (Since April 14)
        * Upload a bin corresponding with the installed build / board using OTA update
        * Check if upload successful
        * Reboot
        * Check if newest version is installed (build)
* Check the [StarLeds test scenarios](/StarDocs/StarLeds/Testing/)
* 🚧
