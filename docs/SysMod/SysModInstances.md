---
title: SysMod Instances
hide:
  # - navigation
  # - toc
---

Instances: System view:

<img width="363" alt="Screenshot 2024-04-23 at 21 52 33" src="https://github.com/ewowi/StarDocs/assets/138451817/f5719954-52cc-4caa-8339-d7e549d9c2bb">

Instances: Dashboard view:

<img width="882" alt="Screenshot 2024-04-23 at 21 46 58" src="https://github.com/ewowi/StarDocs/assets/138451817/2d49f218-7bf3-4c13-bdfc-f013ccff44cb">

## SysMod Instances

The instance module show all the StarMod instances in the network.

* In the System view version and uptime is shown
* In the Dashboad view "dash" variables are shown, the dmx start channel and the Sync master
    * Dash variables: variables where the dash property is set to true. The on/off variable is typically a dash variable. In StarModLed, brightness is a dash variable.
    * DMX start channel: only visible if the e131 usermod module is compiled (per default). Dash variables can be controlled via DMX (🚧)
    * Sync Master: StarMod instances can control each-others dash variables. A sync master controls the variables of instances set to this sync master.
* The dashboard view is used to control other instances from an instance
* Dash variables makes it easy for StarMod applications (like StarModLeds) to define which variables are used for central control, whether it is done by the dashboard view, dmx or also Home Automation. Only thing StarMod applications need to define is the dash property, all functionality is implemented by StarMod (core).

## dev

'''
    JsonObject currentVar = ui->initCheckBox(parentVar, "on", true, false, [](JsonObject var, unsigned8 rowNr, unsigned8 funType) { switch (funType) { //varFun
      case f_UIFun:
        ui->setLabel(var, "On");
        return true;
      case f_ChangeFun:
        //implement on/off behaviour
        return true;
      default: return false;
    }});
    currentVar["dash"] = true;
'''

🚧
