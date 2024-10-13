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

# Welcome to StarMod

StarMod is designed for FreeRTOS, the underlying operating system of ESP32. Starmod consists of modules. Everything is a module. StarMod serves as the base of multiple GitHub repositories for different purposes:

* [StarBase](https://github.com/ewowi/StarBase) is the upstream repository containing generic functionality. This works right out of the box. StarBase can be forked to build custom networked applications for microcontrollers.
* [StarLight](https://github.com/MoonModules/StarLight) is a fork from StarBase that includes the parts required to control LEDs. StarBase itself can work without including the LED code.
* Star???? - Everybody can fork StarBase and add new functionality. 

StarMod is made by MoonModules, a group of LED enthusiasts who also made [WLED MM](https://mm.kno.wled.ge) and contribute to [WLED](https://kno.wled.ge) and can be found at [Discord - WLED 2D and audio dev](https://discord.gg/TC8NSUSCdV). Where WLED (MM) is aimed at 1D and 2D effects and fixtures, StarLight is aimed at 2D and 3D effects and fixtures. StarMod has been built from scratch using the experience gained working on WLED (MM).

StarMod will integrate with major IOT/network devices and applications 🚧.

<img width="400" alt="image" src="https://github.com/ewowi/StarBase/assets/138451817/e29cfed8-59b2-4abb-82e4-c26bbec4cde2">

**StarBase System modules**

* Print: Print to different targets (Serial, UI, file, net)
* Files: File Manager, upload files
* Model: Datamodel in json, stored to file, used in ui and network comms
* Network: Wifi 
* Web: Web server
* UI: UI Server
* System: Show and manage ESP32 system, OTA updates

**User Modules**

* E131/DMX support
* Home Assistant (planned)
* ...

**Build apps on top of this by forking StarBase**

* LED apps (StarLight)

  <img width="316" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/d48679eb-efbe-4133-b43d-e3f33587530a">

* IO control apps
* IOT apps 
* Controlling your fishtank
* DMX controller
* Any app

See this for more info on StarMod:
[StarMod 💫.pdf](https://github.com/ewowi/StarDocs/files/14837446/Starmod.pdf)

Created by [MoonModules](https://github.com/MoonModules)

StarLight was inspired by [WLED MM](https://github.com/MoonModules/WLED)

**Disclaimer**

Using this software is the users responsibility. The software may include bugs or other defects. Always be careful when handing electricity and know your limits. The contributors of this repository can not be held liable for anything harm arising from the use or misuse of this software, including but not limited to spontaneous combustion of the entire LED strip, the house, and the inevitable heat death of the universe

**GPL V3 License**

You may copy, distribute and modify the software as long as you track changes/dates in source files. Any modifications to or software including (via compiler) GPL-licensed code must also be made available under the GPL along with build & install instructions ([tldrlegal](https://www.tldrlegal.com/license/gnu-general-public-license-v3-gpl-3))

Join the Discord server to discuss everything about StarMod, Starlight, Moon Modules, and Sound Reactive!

<a href="https://discord.gg/TC8NSUSCdV"><img src="https://discordapp.com/api/guilds/700041398778331156/widget.png?style=banner2" width="25%"></a>

© 2024 MoonModules ☾ - StarMod, StarBase and StarLight is licensed under GPL-v3

[Used libraries and dependencies](StarDocs/about/contributors/#used-libraries-and-dependencies)

## MoonModules
<img width="456" alt="20230805-2049-000" src="https://github.com/ewowi/StarDocs/assets/1737159/6e0dd13d-1e1a-4956-98ae-6d1a22b70562">
