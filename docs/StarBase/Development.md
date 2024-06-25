---
title: Development
hide:
  # - navigation
  # - toc
---

## Development

Process

* Check [Contribute](/StarDocs/StarBase/Contribute/)
* Determine if it is a StarBase or StarLight change
* For medium to big changes: create a GitHub issue to document the design of the change
* Fork the appropriate (StarBase or StarLight)
* Create a branch (more text needed here) for medium or big changes (small can be done on main)
* Implement your change
* Follow the [Standards and guidelines](https://ewowi.github.io/StarDocs/StarBase/StandardsAndGuidelines/)
* Create a pull request
* Update StarDocs to document and describe the impact of the change. You can use a link to the commit implementing the change as follows ([2024040511](https://github.com/ewowi/StarBase/commit/4f12da235bcee958b74f6d932b20a5ffcf9c449c) is the version number of the change):

    <img width="300" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/31c591df-9241-49b6-aa71-1a7cd6282a89">

* In case of a StarBase change, propagate the change downstream to StarLight. The git tree will typically look like this (green is downstream, blue is upstream):

    <img width="300" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/562978ff-1d97-4246-938f-501a19dfadec">

* Determine if post merge steps are needed in StarLight (e.g. rerun npm run dev to update html_ui.h)

🚧