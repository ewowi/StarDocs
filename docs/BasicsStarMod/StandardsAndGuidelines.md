---
title: Standards and Guidelines
hide:
  # - navigation
  # - toc
---

## Heading 2

Everything is a module

## Dev

* Orthogonality: concepts are independent or irrelevant to eachother. Examples:

** StarMod Core has no notion of applications build on top of it e.g. StarMod Leds

** No notion of HTML in c(++) code

** Effects have no notion of the type of projection or fixture it is applied to

* Minimize the use of static / global variables in Classes, there are still static class variables which need to be investigated to make non static

