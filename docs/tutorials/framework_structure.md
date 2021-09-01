# Framework Structure

In *Groovin'*, code is split into four five folders: *source*, *source_internal*, *source_internal_mod*, *source_mod*, and *source_mod_lib*.

## /source folder
This folder contains all the original *Friday Night Funkin'* code, and direct mod functionality should *not* be put in any of the code here.
Only small sections of the original code should be changed to expand the framework functionality.
This is necessary to keep the code easily portable to newer versions of *Friday Night Funkin'*.

## /source_internal
This folder contains all the code for *Groovin'*. 
Functionality that handles how mods are executed and classes that belong to the framework itself should go in here.
Modders should not touch this folder either. 
If there is an absence of a modding functionality, such as a missing *mod hook* (we'll get into what that is later), modders may add it and are encouraged to pull request their additions to the framework.

## /source_internal_mod
This folder contains all the code for internal mods of *Groovin'*. 
Internal mods are mods that come **bundled** with *Groovin'* and that are common necessities for a proper "engine".
Some examples of internal mods include *Groovin Input*, which likens the input system to other rhythm games and provides quality-of-life features like a hit error bar, and *Schmovin*, which is reponsible for **all** the modcharting functionality for *Groovin'*.
This is the folder that the Groovin' Team would deal with the most, so, like the */source* folder, mod functionality should not be put in here.

## /source_mod
This is the folder where all mod code belongs. It's also where modders are able to configure some settings about the framework.
*ModReferences.hx* and *FrameworkConfig.hx* are the most important files here.

*ModReferences.hx* references all the mods that shall be included or forced in the build. 
It's necessary to reference each mod that will be used in the build by adding the class name to Ref() so that the mod class does not get eliminated during compilation (*see [Dead Code Elimination](https://haxe.org/manual/cr-dce.html)*).

*FrameworkConfig.hx* contains some changeable constants for the framework.

## /source_mod_lib
This folder usually remains unused but is meant to be a place for external Haxe libraries for Groovin' mods that don't want to put libraries in their package.