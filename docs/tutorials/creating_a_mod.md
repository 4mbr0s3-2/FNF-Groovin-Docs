# Creating a Mod
*Note: Groovin's way of doing mods is way different from other Friday Night Funkin' engines. If you're familiar with other game mod loaders, you'll see some similarity.*

## Foreword
If you're familiar with modding in Kade Engine or Modding Plus or have watched tutorials for them on making custom characters, weeks, songs, mechanics, *throw everything you know about those out the window*, because we're (almost) *never going to touch the original game's code*. It's about to get freaky... *(on a friday night yeah)*

## Creating a Mod
Naming Convention: Folders will always be in *snake_case*, while code files and classes will always be in *UpperCamelCase*.

If you know that your mod is going to have big systems of original code that loosely interact with each other (see some of the internal mods to judge if your mod is like that), make a folder for the mod under */source_mod*, and make some appropriate subfolders for the mod (/note_mods, /themes, /shaders).

Otherwise, if you know that your mod is going to be just a week with three songs, you can make one file under */source_mod*.

## Boilerplate code
```haxe
class ExampleMod extends Mod
{
	override function Initialize()
	{
        // Insert your mod hooks here, and other initialization things...
	}

	override function ShouldRun():Bool
	{
        // Only run this mod if the week's stage matches this mod.
		if (Type.getClass(FlxG.state) == PlayState)
		{
			return PlayState.curMod == this && PlayState.isModdedStage;
		}
		return false;
	}
}
```

The *ShouldRun* method indicates if most of the mod's functions can run within the PlayState state, or the actual gameplay state.

For a mod meant to be only run on its own stages, the boilerplate code should be kept.
Otherwise, for a mod that can be run on any stage, such as *Groovin' Input*, *ShouldRun* should always return *true*.