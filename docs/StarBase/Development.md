---
title: Development
hide:
  # - navigation
  # - toc
---

## Development

Process

* Check [Contribute](/StarDocs/StarBase/Contribute/)
* Decide if it is a StarBase or StarLeds change
* For Medium to big changes: create a github issue to document the design of the change
* Fork one of the repos (StarBase or StarLeds)
* Create a branch (more text needed here) for medium or big changes (small can be done on main)
* Implement change
* Follow the [Standards and guidelines](https://ewowi.github.io/StarDocs/StarBase/StandardsAndGuidelines/)
* Create a pull request
* Update StarDocs to document the impact of the change. You can use a link to the commit implementing the change as follows ([2024040511](https://github.com/ewowi/StarBase/commit/4f12da235bcee958b74f6d932b20a5ffcf9c449c) is the version nr of the change):

    <img width="300" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/31c591df-9241-49b6-aa71-1a7cd6282a89">

* In case of a StarBase change, propagate the change downstream to StarLeds. Git tree will typically look like (green is downstream, blue is upstream):

    <img width="300" alt="image" src="https://github.com/ewowi/StarDocs/assets/138451817/562978ff-1d97-4246-938f-501a19dfadec">

* Check if post merge steps are needed in StarLeds (e.g. rerun npm run dev to update html_ui.h)

🚧
