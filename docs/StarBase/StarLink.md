---
title: StarLink
hide:
  # - navigation
  # - toc
---

## StarLink

StarLink is the current name for the module that allows for multiple instances to be linked together (until we got sued).

Its origin can be found in WLED-MoonModules and is called Super-Sync there, other names used are Mega-Sync, Ultra-Sync etc.

In StarBase (and it's forks), StarLink is a distributed system meaning there is no sync master (there is in WLED) but instances are part of a group. A group is specified by an instance name identified by a hyphen: groupname-instancename.

<img width="455" alt="Screenshot 2024-05-23 at 20 50 02" src="https://github.com/ewowi/StarDocs/assets/138451817/e3dbd019-6193-4081-aad1-63f178d396ac">

The Link columns shows group info:

* 0: There is no hyphen in the name, so this instance is not part of any group
* 1: This instance has a group name but there are no other instances in the network with the same groupname
* 2 or more: This instance is part of a group (the nr is the nr of instances in the group)

Note that an instance in a group can be down, but as soon as the instance recovers, it will rejoin the group.

StarLink functionality is active if there are 2 or more instances in a group. This means that all dash variables (Variables which will show up in the dashboard 🚧) and it's children will be synchronized between all instances of the group. It doesn't matter in which instance of the group it will be changed, all other instances will be updated if it's changed.

In the StarBase demoApp, On, Brightness and DMX channel are currently dash variables. In StarLeds, FX (and it's children/controls), projection (and it's children) are currently dash variables.

On a group of sticks this looks as follows:

<video width="650" autoplay><source src="https://github.com/ewowi/StarDocs/assets/138451817/36d8a25d-c3cb-40d1-953a-330e06db9983" type="video/mp4"></video>

(In this video, there are 2 RGBW sticks which behave a bit differently)

## 🚧

Above is the current state of StarMod/StarLeds.

Below is the work in progress:

* IP, mac-address, name: Mac-address will be the id to store info of other instances in an instance (unchangeable), IP is used to access an instance (can change), instance name is the user friendly name of an instance (and used for grouping)
* Position: Each instance will have a position which is used to order instances
* Synchronized Time: Each instance will have the same time in milliseconds, will have the same random seed and therefore in StarLeds, effects will run exactly the same.
* StarLeds - Distributed effect: using ordered instances, multiple instances can each run part of an effect - scalibility, depending on the effect:
    * Only the displayed part can be rendered. also random seeds helps here
    * Displayed part plus a bit needs to be rendered
    * The whole effect must be rendered.
    * Note: rendering the effect without showing it on leds is much faster, eg game of life about 10 times faster
