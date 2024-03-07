---
title: Projections
hide:
  # - navigation
  # - toc
---

## Projections

Text

### Projections cases


```
switch (leds->effectDimension) {
  case _1D:
    switch(projectionDimension) {
      case _1D: //1D1D
      case _2D: //1D2D
      case _3D: //1D3D
    }
  case _2D:
    switch(projectionDimension) {
      case _1D: //2D1D
      case _2D: //2D2D
      case _3D: //2D3D
    }
    break;
  case _3D:
    switch(projectionDimension) {
      case _1D: //3D1D
      case _2D: //3D2D
      case _3D: //3D3D
    }
    break; //effectDimension _3D
} //effectDimension
```

<video width="248" autoplay><source src="https://github.com/ewowi/StarDocs/assets/1737159/637588d2-0f38-46ba-b765-a37acf5fd385" type="video/mp4"></video>
