---
title: Development
hide:
  # - navigation
  # - toc
---

## Development

Process

* Check [Contribute](/StarDocs/BasicsStarMod/Contribute/)
* Decide if it is a StarMod (Core) or StarMod Leds change
* For Medium to big changes: create a github issue to document the design of the change
* Fork one of the repos (StarMod Core or Leds)
* Create a branch (more text needed here)
* Implement change
* Follow the [Standards and guidelines](https://ewowi.github.io/StarDocs/BasicsStarMod/StandardsAndGuidelines/)
* Create a pull request
* Update StarDocs to describe the impact of the change. You can use a link to the commit implementing the change as follows (2024040511 is the version nr of the change):

![image](https://github.com/ewowi/StarDocs/assets/138451817/31c591df-9241-49b6-aa71-1a7cd6282a89)

* In case of a StarMod (Core) change, propagate the change downstream to StarModLeds. Git tree will typically look like( green is downstream, blue is uostream):

![image](https://github.com/ewowi/StarDocs/assets/138451817/562978ff-1d97-4246-938f-501a19dfadec)

* Check if post merge steps are needed in StarMod Leds (e.g. rerun npm run dev to update html_ui.h)

🚧
