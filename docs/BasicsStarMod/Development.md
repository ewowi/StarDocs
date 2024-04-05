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
* Implement change
* Follow the [Standards and guidelines](https://ewowi.github.io/StarDocs/BasicsStarMod/StandardsAndGuidelines/)
* Create a pull request
* Update StarDocs to describe the impact of the change

pic 

* In case of a StarMod (Core) change, propagate the change downstream to StarModLeds. Git tree will typically look like:

pic

    * Check if post merge steps are needed in StarMod Leds (e.g. rerun npm run dev to update html_ui.h)

🚧