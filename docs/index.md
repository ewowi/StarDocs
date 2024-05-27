---
title: Welcome to StarMod
hide:
  - navigation
  - toc
---

<p align="center">
  <a href="https://github.com/ewowi/StarBase/releases"><img src="https://img.shields.io/github/release/ewowi/StarBase.svg?style=flat-square"></a>
  <a href="https://raw.githubusercontent.com/ewowi/StarBase/main/LICENSE"><img src="https://img.shields.io/github/license/ewowi/StarBase?color=blue&style=flat-square"></a>
  <a href="https://starmod.discourse.group"><img src="https://img.shields.io/discourse/topics?colorB=blue&label=forum&server=https%3A%2F%2FStarMod.discourse.group%2F&style=flat-square"></a>
  <a href="https://discord.gg/TC8NSUSCdV"><img src="https://img.shields.io/discord/700041398778331156.svg?colorB=blue&label=discord&style=flat-square"></a>
  <a href="https://github.com/ewowi/StarBase"><img src="https://img.shields.io/badge/source-github-blue.svg?style=flat-square"></a>
  <a href="https://github.com/ewowi/StarBase-App"><img src="https://img.shields.io/badge/app-StarMod-blue.svg?style=flat-square"></a>
  <a href="https://gitpod.io/#https://github.com/ewowi/StarBase"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?style=flat-square&logo=gitpod"></a>
</p>

<img width="400" alt="image" src="https://github.com/ewowi/StarBase/assets/138451817/e29cfed8-59b2-4abb-82e4-c26bbec4cde2">

# Welcome to StarMod

StarMod is for freeRTOS (the underlying operating system of ESP32) what Windows is for MSDos: a layer on top of it what makes programming applications easier. The layer consists of modules: everything is a module. 

StarMod consists of multiple github repositories:

* [StarBase](https://github.com/ewowi/StarBase): The upstream repo containing generic functionality. This works right out of the box. StarBase can be forked to build custom applications.
* [StarLeds](https://github.com/MoonModules/StarLeds): Fork from StarBase adding Leds specific functionality. (There is no notion of LEDs whatsoever in StarBase)
* Star????: Everybody can fork StarBase and add new functionality. 

StarMod will integrate with major IOT/network devices and applications 🚧.

StarBase System modules:

* Print: Print to different targets (Serial, UI, file, net)
* Files: File Manager, upload files
* Model: Datamodel in json, stored to file, used in ui and network comms
* Network: Wifi 
* Web: Web server
* UI: UI Server
* System: Show and manage ESP32 system, OTA updates

User Modules

* E131/DMX support
* Home Assistant (planned)
* ...

Build apps on top of this by forking StarBase

* Led apps (StarLeds)

  <img width="316" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/d48679eb-efbe-4133-b43d-e3f33587530a">

* IO control apps
* IOT apps 
* Controlling your fishtank
* DMX controller
* Any app

See this for more info on StarMod:
[StarMod 💫.pdf](https://github.com/ewowi/StarDocs/files/14837446/Starmod.pdf)

By [MoonModules](https://github.com/MoonModules)

StarLeds inspired by [WLED MM](https://github.com/MoonModules/WLED)

Disclaimer:

Using this software is the users responsibility as it is not bug free. Therefore contributors of this repo can not be held reliable for anything including but not limited to spontaneous combustion of the entire led strip, the house and the inevitable heat death of the universe

GPL V3 License:

You may copy, distribute and modify the software as long as you track changes/dates in source files. Any modifications to or software including (via compiler) GPL-licensed code must also be made available under the GPL along with build & install instructions ([tldrlegal](https://www.tldrlegal.com/license/gnu-general-public-license-v3-gpl-3))

Join the Discord server to discuss everything about StarMod MM and SR!

<a href="https://discord.gg/TC8NSUSCdV"><img src="https://discordapp.com/api/guilds/700041398778331156/widget.png?style=banner2" width="25%"></a>

© 2024 MoonModules ☾ - StarMod, StarBase and StarLeds is licensed under GPL-v3

[Used libraries and dependencies](https://ewowi.github.io/StarDocs/about/contributors/#used-libraries-and-dependencies)

## MoonModules
<img width="456" alt="20230805-2049-000" src="https://github.com/ewowi/StarDocs/assets/1737159/6e0dd13d-1e1a-4956-98ae-6d1a22b70562">
