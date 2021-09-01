# Asset Structure

## /mod_assets
Much like modders should not touch */source*, modders should also not touch */assets*. Instead, modders should add mod assets under */mod_assets* (obviously).
The following sections will cover different folders under */mod_assets*.

## Folder Structure
Assets for any mod should be put under a folder of the same name as the mod's class name.
For example, a .json chart for the song example-song for ExampleMod should be put under `/mod_assets/data/ExampleMod/example-song/example-song.json`.

### /data
All of a mod's charts should be stored here.
### /weeks
All of a mod's song assets should be stored here.
### /songs
All of a mod's music files should be stored here.
### /shared
This folder is reserved for the Groovin' framework.

## /preload
The */preload* folder contains the same structure as its parent folder, */mod_assets*, but all assets under it are pre-loaded and, in-game, accessed through the *root* instead of */preload.*
For example, an image in `/mod_assets/preload/images/image.png` should be accessed in-game with `/mod_assets/images/image.png`.