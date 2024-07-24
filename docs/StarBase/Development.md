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

## Live Server
July 24, 2024

StarBase htm, js and css files can be previewed directly using the Live Server plugin. This makes UI development faster as no need to compile flash and run on esp32 each time.

Step 1: Install the plugin and restart VSCode

<img width="466" alt="Screenshot 2024-07-24 at 18 20 22" src="https://github.com/user-attachments/assets/0c4d4d27-d275-420c-9483-53f36f6dcd8b">

Step 2, select an htm file and right click Open with Live Server

<img width="439" alt="Screenshot 2024-07-24 at 18 20 05" src="https://github.com/user-attachments/assets/8b8d89d5-a8aa-4866-8e41-7d0e06665f2e">

Step 3: see the result in your browser (127.0.0.1)

<img width="1417" alt="Screenshot 2024-07-24 at 18 20 39" src="https://github.com/user-attachments/assets/44a0ab83-7172-4fa8-94ee-50217a8318a0">

Note 1: This live view uses the model.json file to get the module data

Note 2: Functionality is limited yet: it now shows the UI elements without the data

## HTML compression
July 24, 2024

htm, js and css files are compressed into html_ui.h and html_newui.h files when compiled and flashed. By this memory footprint is smaller and also these files are not on the esp32 fileserver but flashed as compiled c code.

The magic for this is done in cdata.js and webbundle.py. Both files can be found in the tools folder.

npm needs to be installed and also npm ci (or npm install) - tbd: difference between ci and install?

installing npm is a manual task to be done by a developer (instructions?) but the rest is done by the webbundle.py script.

(previously a developer must execute npm ci (or npm install) and npm run build (or npm run dev) on the command prompt)
