---
title: Projections
hide:
  # - navigation
  # - toc
---

## Projections

Text

## Dev

### Projections cases
(LedFixture.cpp - projectAndMap)

Projection is depending on the dimension of the effect and the dimension of the projection, 1D, 2D or 3D.
This means there are 9 different cases.

Each physical pixel will be mapped to a logical pixel using these cases.

Currently the following is done (default projection)

```
switch (effectDimension) {
  case _1D:
    switch(projectionDimension) {
      case _1D: //1D1D: Distance from point (default 0) on a line
      case _2D: //1D2D: Distance from point (default 0) on a matrix
      case _3D: //1D3D: Distance from point (default 0) on a cube
    }
  case _2D:
    switch(projectionDimension) {
      case _1D: //2D1D: all rows adjacent to eachother
      case _2D: //2D2D: identical
      case _3D: //2D3D: x = x+y, y = z
    }
    break;
  case _3D:
    switch(projectionDimension) {
      case _1D: //3D1D all rows and columns adjacent to eachother (wip)
      case _2D: //3D2D: (wip)
      case _3D: //3D3D: identical (wip)
    }
    break; //effectDimension _3D
} //effectDimension
```

Other projections are applied at different moments
* Center: 1D effect: point in distance from point
* Center: 2D effect: reverse mapping: which XYZ(centric) map the default mapping
* Multiply: adjust size, pixel % adjusted size
* Rotation: during XYZ()
* ...

<video width="248" autoplay><source src="https://github.com/ewowi/StarDocs/assets/1737159/637588d2-0f38-46ba-b765-a37acf5fd385" type="video/mp4"></video>
