---
title: LedModEffects
hide:
  # - navigation
  # - toc
---

## Heading 2

Text

## Effects

<img width="158" alt="Screenshot 2024-03-05 at 11 03 46" src="https://github.com/ewowi/StarDocs/assets/1737159/c2fac19d-3417-4aeb-b809-816850195957">

An effect can have multiple tags, tags are shown in the drop down. Any tag is possible, not necessarily limited to 1D, 2D, sound, etc

Current tags

♪ Audio Volume 

♫ Audio Frequency

┊1D

▦ 2D

🧊3D

💫StarMod 

⚡FastLed origin

💡WLED origin

### Dev

Defined in Effect class as follows:

```
  const char * name() {return "GEQ";}
  unsigned8 dim() {return _2D;}
  const char * tags() {return "💡♫";}
```

### Other info

* [Mappings](/StarDocs/BasicsLed/Mappings.md)

* [Projections](/StarDocs/BasicsLed/Projections.md)

