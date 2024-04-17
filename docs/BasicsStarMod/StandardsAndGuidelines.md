---
title: Standards and Guidelines
hide:
  # - navigation
  # - toc
---

## Standards and Guidelines

* Orthogonality: concepts are independent or irrelevant to eachother. Examples:
    * StarMod Core has no notion of applications build on top of it e.g. StarMod Leds
    * No notion of HTML in c(++) code
    * Effects have no notion of the type of projection or fixture it is applied to
    * Any projection can be applied to any effect in any fixture, 1D to 3D in any combination
    * Modules are as independent from each other as possible (but they can call each other)
* Everything is a module, every module is a (singleton) class
* Code of a module is in the module class
* Minimize the use of static / global variables. Use modules classes to define variables
* "functional locality": code of a feature is in one place, not in different files etc.
* Model.json for variables and UI generation
* Minimize model json size
    * UiFun: send labels and comments and select options instead of storing in model
* Variables are defined using init<Type> functions containing a function paramater for:
    * f_ValueFun: assigning default values
    * f_UIFun: called by the UI to get extra info (label, comment, options)
    * f_ChangeFun: called if the value of a variable changes, use old and new value
    * f_LoopFun: executed in loop e.g. preview
    * f_AddRow: called if a row is added (Variable is in table)
    * f_DelRow: called if a row is deleted (Variable is in table)
    * At the moment of writing, var names need to be unique along the whole project!
* UI is 100% generated from model and UIFun, only app.js can be used to implement specific functionality. UI can be single elements or tables with elements and can be hierarchical just like html is hierarchical. UI elements may only be created using init<Var> calls. If another UI construct is needed or specific node hierarchy is not implemented yet, please log a github issue.
* Minimize on heap and stack use
    * Effect class doesn't have local variables
    * init Variable: functions, not classes
* Pragmatic use of Design Patterns (e.g. Singleton) and OO concepts - aiming at maximal efficiency in ESP32 environment
* Keep it simple to start with, build from there
    * [MVP (Minimum Viable Product)](https://en.wikipedia.org/wiki/Minimum_viable_product) concept
    * Copy - refactor - paste: copy code from the internet -> apply mvp -> apply standards and guidelines - paste in StarMod
    * Code should be as readable as possible
        * Minimal code lines
        * Only .h (not .cpp) if possible, as it might be a nice c practive but makes code less easier to read (less compact, defaults only in .h) and maintain
        * No get/set like function wrappers around variables
* Other standards and guidelines yet to be written down ;-)
* These standards and guidelines should result in the posibility to create a complete new service by creating one module in one .h file allowing it to use all functionality available in StarMod. Including UI, pins, files, print, model persistent storage, enabling and disabling, loop injection etc. If you feel it's not possible, log a github issue.
* These standards and guidelines are not unchangeable and can be disputed, eg singletons, minimal code. but its just the way things are done now to have an initial lean and mean standard. Changes to the standards can be proposed in github issues
