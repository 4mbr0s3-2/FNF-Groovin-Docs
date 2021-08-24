# Environment Setup

*Note: Most of the following document is adopted from Friday Night Funkin's official README.md, but take some time to read the extra setup at the bottom!*

### Installing the Required Programs

First you need to install Haxe and HaxeFlixel.  
1. [Install Haxe 4.1.5](https://haxe.org/download/version/4.1.5/)
2. [Install HaxeFlixel](https://haxeflixel.com/documentation/install-haxeflixel/) after downloading Haxe

Other installations you'd need is the additional libraries, a fully updated list will be in `Project.xml` in the project root. Currently, these are all of the things you need to install:
```
flixel
flixel-addons
flixel-ui
hscript
newgrounds
```
For each of these, run `haxelib install [library]`.

You'll also need to install a couple things that involve Gits. To do this, you need to do a few things first.
1. Download [git-scm](https://git-scm.com/downloads). Works for Windows, Mac, and Linux, just select your build.
2. Follow instructions to install the application properly.
3. Run `haxelib git polymod https://github.com/larsiusprime/polymod.git` to install Polymod.
4. Run `haxelib git discord_rpc https://github.com/Aidan63/linc_discord-rpc` to install Discord RPC.

You should have everything ready for compiling the game! Follow the guide below to continue!

At the moment, you can optionally fix the transition bug in songs with zoomed out cameras.
- Run `haxelib git flixel-addons https://github.com/HaxeFlixel/flixel-addons` in the terminal/command-prompt.

### Ignored files

The API keys for the game are gitignore'd, but, because of that, the game doesn't compile without them.

Just make a file in `/source` and call it `APIStuff.hx`, and copy-paste this into it:

```haxe
package;

class APIStuff
{
	public static var API:String = "";
	public static var EncKey:String = "";
}

```

and you should be good to go there.

### Compiling game

The original README.md instructed to use command prompt to compile, but there's an easier way.

#### VS Code's Run and Debug

You can automagically configure the Lime project to allow Visual Studio Code to instantly debug the game by running `flixel configure . -ide vscode` on the root folder after installing the [Lime extension](https://marketplace.visualstudio.com/items?itemName=openfl.lime-vscode-extension). 

You can read more about setting up with Visual Studio Code setup [here](https://haxeflixel.com/documentation/visual-studio-code/).

#### Original Command Prompt Way

Once you have all those installed, it's pretty easy to compile the game. You just need to run 'lime test html5 -debug' in the root of the project to build and run the HTML5 version. (command prompt navigation guide can be found here: [https://ninjamuffin99.newgrounds.com/news/post/1090480](https://ninjamuffin99.newgrounds.com/news/post/1090480))

To run it from your desktop (Windows, Mac, Linux) it can be a bit more involved. For Linux, you only need to open a terminal in the project directory and run 'lime test linux -debug' and then run the executable file in export/release/linux/bin. For Windows, you need to install Visual Studio Community 2019. While installing VSC, don't click on any of the options to install workloads. Instead, go to the individual components tab and choose the following:
* MSVC v142 - VS 2019 C++ x64/x86 build tools
* Windows SDK (10.0.17763.0)

Once that is done you can open up a command line in the project's directory and run `lime test windows -debug`. Once that command finishes (it takes forever even on a higher end PC), you can run FNF from the .exe file under export\release\windows\bin
As for Mac, 'lime test mac -debug' should work, if not the internet surely has a guide on how to compile Haxe stuff for Mac.
