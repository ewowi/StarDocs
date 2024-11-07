---
title: Standards and Guidelines
hide:
  # - navigation
  # - toc
---

## Standards and Guidelines

* Orthogonality: concepts are independent or irrelevant to eachother. Examples:
    * StarBase has no notion of applications build on top of it e.g. StarLight
    * No notion of HTML in c(++) code
    * Effects have no notion of the type of projection or fixture it is applied to
    * Any projection can be applied to any effect in any fixture, 1D to 3D in any combination
    * Modules are as independent from each other as possible (but they can call each other)
* Everything is a module, every module is a (singleton) class
* Code of a module is in the module class
* Minimize the use of static / global variables. Use modules classes to define variables
* "functional locality": code of a feature is in one place, not in different files etc.
* JSON (powered by ArduinoJSON v7 ! and StarJson for highspeed low mem read) as the default way to store and comminicate data 
* Model.json for variables and UI generation
* Minimize model json size
    * onUI: send labels and comments and select options instead of storing in model
* Variables are defined using init<Type> functions containing a function paramater for:
    * onSetValue: assigning default values
    * onUI: called by the UI to get extra info (label, comment, options)
    * onChange: called if the value of a variable changes, use old and new value
    * onLoop: executed in loop e.g. preview
    * onLoop1a: once per second
    * onAdd: called if a row is added (Variable is in table)
    * onDelete: called if a row is deleted (Variable is in table)
    * ~~At the moment of writing, var names need to be unique along the whole project!~~ combination of parent id and id needs to be unique
* UI is 100% generated from model and onUI, only app.js can be used to implement specific functionality. UI can be single elements or tables with elements and can be hierarchical just like html is hierarchical. UI elements may only be created using init<Var> calls. If another UI construct is needed or specific node hierarchy is not implemented yet, please log a github issue.
* Minimize on heap and stack use
    * Effect class doesn't have local variables
    * init Variable: functions, not classes
* Pragmatic use of Design Patterns (e.g. Singleton) and OO concepts - aiming at maximal efficiency in ESP32 environment
* Keep it simple to start with, build from there
    * [MVP (Minimum Viable Product)](https://en.wikipedia.org/wiki/Minimum_viable_product) concept
    * Copy - refactor - paste: copy code from the internet -> apply mvp -> apply standards and guidelines - paste in StarBase
    * Code should be as readable as possible
        * Minimal code lines
        * ~~Only .h (not .cpp) if possible, as it might be a nice c practive but makes code less easier to read (less compact, defaults only in .h) and maintain~~, see below
        * No get/set like function wrappers around variables
* Strictly forbidden for frameworks like Angular Vue React and the like
* These standards and guidelines should result in the posibility to create a complete new service by creating one module in one .h file allowing it to use all functionality available in StarBase. Including UI, pins, files, print, model persistent storage, enabling and disabling, loop injection etc. If you feel it's not possible, log a github issue.
* These standards and guidelines are not unchangeable and can be disputed, eg singletons, minimal code. but its just the way things are done now to have an initial lean and mean standard. Changes to the standards can be proposed in github issues
* A lot of good stuff is in here [The C++ Programming Language Bjarne Stroustrup, 3rd edition](https://gist.github.com/victormwenda/6bb04802d65eaab11a724ac4b04dd9e6). Maybe some notes on esp32 specific programming?
    * See [stroustrup Chapter25 on embedded systems](https://www.stroustrup.com/PPPslides/25_embedded.ppt) 
    * We prefer char * over String especially if you don't know what you are doing - which is a contradiction as strings can cause defrag and chars can cause crashes ;-)
    * Globals useful to put them in designated memory area?
* Heap memory changes should be as minimal as possible and processing should be done on the stack (as that is cleared after each code block has finished). So heap should be used to store more the ‘data model’, which is more or less stable data. Like leds[] or mapping tables or Executables. Any processing can modify this but should use heap only to modify the ‘data model’. This then means that any structure (struct, class, containers) other then the data model should be avoided, best example is string but also vector should be used with great care as they might be classes on itself but inside their classes they do heap allocation and free and that is the tricky part. There are several ways to do this. Next to char string use of pointers or values by reference. Eg you can loop over a vector where each element is copied in the loop but you can also make each element a pointer to the element in the ‘data model’. Eg for (auto &element: executablesVector) or void function(ClassType &var). The & sign makes sure there is not vector or class element copy
*  An object (and also struct) takes just the memory space of the variables it defines, the Variable object is one pointer and tons of code, Effect and Projection object is not allowed to have variables to minimize the overhead. They have overloaded virtual functions though, memory for function pointer will be allocated to admin this.
* StarBase and StarLight have next to the main branch also a dev branch where all development will be done on, optionally branches from dev can be made for multi commit changes. All merging from dev to main must be done by pull requests so the release changes will automatically be propagated with the commits made into main
* For files which are included in other files: All definition stuff should go into cpp files.
    * Compiling goes faster as an include will only include the header contents
    * not having .cpp means the whole interdependency is very fragile, changes cause ‘multiple definitions / first define here’ errors
    * in .h files you don’t need to define all the includes as an include will also include what the includer included , which relates to 2 and is not very clean/clear
    * A small .h file serves as documentation and gives a quick overview of what is there
