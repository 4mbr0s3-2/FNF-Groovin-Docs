# Introduction
Welcome to the Groovin' Mod Framework Documentation!
Here, you'll find some useful resources that'll get you _in the groove_ of utilizing the framework as well as some additional information about this "mod template."

## About
Groovin' is a starting template for mods that focuses on ease-of-use and organization. It is *not* an engine by itself, but it comes bundled with toggleable mods that polish some of the original game's systems, such as *Groovin' Input*, and add more functionality to the game, such as [Razer Chroma](https://www.razer.com/chroma) support. It was originally made by [4mbr0s3 2](https://www.youtube.com/channel/UCez-Erpr0oqmC71vnDrM9yA/videos) as a test to decouple "mod" code from the original game's code, and [Bopeebo Rumble](https://gamebanana.com/mods/44720) was a test for this workflow.

## Goals
Two main goals for the project are to decouple user mod code from the original game and to facilitate porting mods into future versions of [Friday Night Funkin'](https://www.newgrounds.com/portal/view/770371). Edits to the original game's code should be kept to a minimum in order to make porting to future FNF versions easier.

## Open / Closed Principle is Key
Groovin' attempts to follow the [*Open / Closed Principle*](https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle) as closely as possible, which means that it attempts to allow modding functionality without making it necessary for mods to directly modify the source code. By structuring the framework this way, it becomes easier to port into newer versions of Friday Night Funkin' since the original source has not changed significantly. However, it may be more difficult to modify already existing game elements with Groovin' since user code is meant to be executed outside of the game's original code.

For instance, mods made in [_Kade Engine_](https://github.com/KadeDev/Kade-Engine) or [_Project FNF_](https://github.com/aflacc/ProjectFNF) can very easily change the color of the health bar through parameter or variable changes to `PlayState.hx`, but, with Groovin', mods should change the health bar's color by calling `FlxBar.createFilledBar()` after the initialization of it rather than changing the original code directly.

In summary, modding existing game systems with Groovin' can be quite difficult compared to other engines since modifying the source directly is discouraged. However, following SOLID principles and separating mod code from the original game's code can significantly declutter mod projects and make programming more agile.

## FAQ

**Will this project be prepared for when the *full-ass* game comes out?**

We (I) have no idea.

**Is it *Groovin'* or *Groovin*?**

Either one works.