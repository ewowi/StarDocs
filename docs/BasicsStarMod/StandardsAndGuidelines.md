---
title: Standards and Guidelines
hide:
  # - navigation
  # - toc
---

## User

* Everything is a module

## Dev

* Orthogonality: concepts are independent or irrelevant to eachother. Examples:
    * StarMod Core has no notion of applications build on top of it e.g. StarMod Leds
    * No notion of HTML in c(++) code
    * Effects have no notion of the type of projection or fixture it is applied to
    * Any projection can be applied to any effect in any fixture, 1D to 3D in any combination
    * Modules are as independent from each other as possible (but they can call each other)
* Everything is a module, every module is a class
* Code of a module is in the module class
* Minimize the use of static / global variables. Use modules classes to define variables
* "functional locality": code of a feature is in one place, not in different files etc.
* Model.json for variables and UI generation
* Minimize model json size
    * UiFun: send labels and comments and select options instead of storing in model
* Variables are defined using init<Type> functions containing a function paramater for:
    * f_ValueFun: assigning and updating values
    * f_UIFun: called by the UI to get extra info (label, comment, options)
    * f_ChangeFun: called if the value of a variable changes
    * f_LoopFun: executed in loop e.g. preview
    * f_AddRow: called if a row is added (Variable is in table)
    * f_DelRow: called if a row is deleted (Variable is in table)
* Minimize on heap and stack use
    * Effect class don't have local variables
    * init Variable: functions, not classes
* Pragmatic use of Design Patterns (e.g. Singleton) and OO concepts - aiming at maximal efficiency in ESP32 environment
* Code should be as readable as possible
    * Minimal code lines
    * Only .h (not .cpp) if possible, as it might be a nice c practive but makes code less easier to read (less compact, defaults only in .h) and maintain
    * No get/set like function wrappers around variables
* Other standards and guidelines yet to be written down 🤭
