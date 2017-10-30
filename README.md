# SETools - Maya (v2.3.1)

A .SE format import / export plugin for Maya (2014+)

(Maya 2012 works, however some animations have interpolation bugs due to an unfixed Maya bug)

*.SE formats are open-sourced formats optimized for next-generation modeling and animation. They are free to be used in any project, game, software, etc with the hopes that people will adapt the standard unlike other formats available.*

- Animation format documentation: [Specification](https://github.com/SE2Dev/SEAnim-Docs)
- Model format documentation: [Coming soon](#)

## Installation:

Download the latest [seanim.py](https://raw.githubusercontent.com/dtzxporter/SETools/master/seanim.py) and [SEToolsPlugin.py](https://raw.githubusercontent.com/dtzxporter/SETools/master/SEToolsPlugin.py) from the repo and save them in the following directory depending on your OS and Maya version:
- 32bit Windows: C:\Program Files(x86)\AutoDesk\Maya-ver\bin\plug-ins\
- 64bit Windows: C:\Program Files\AutoDesk\Maya-ver\bin\plug-ins\

Next, you must open the plugin manager using `Window->Settings/Preferences->Plugin Manager` once there find `SEToolsPlugin.py` and check off the following:
- Loaded (Loads the plugin)
- Auto load (Loads the plugin every launch)

## Updating:

Replace the files in the correct directory from the installation section with the new ones AND delete all of the `.pyc` files. Go to "SE Tools->Reload" Plugin to finish. If an error occurs, you must simply reload Maya.

## Usage:

*Animations:*
- To import an anim use "SE Tools -> Import SEAnim" or drag and drop a file, this will import an anim onto an already binded scene.
- To export, either select the bones to use (or select none for all), set the end scene time to the animation end time, then use "SE Tools -> Export SEAnim" this will export the animation to a .seanim file.
- To place a notetrack use "SE Tools -> Place Notetrack" this will place a notetrack named "new_notetrack" at the current scene time, you can rename it using the object browser on the left.

*Models:*
- Coming soon

## Changelog:

*v2.3.1:*
- Fixed support for conversion rigs

*v2.3:*
- Support for keyframe cache, which won't fully delete keyframes
- To clear cached keyframes use 'SE Tools->Clear Curves'
- This allows for support for copying keyframes and pasting them later

*v2.2.6:*
- Rewrite of CleanNote names for better support
- Update to newest seanim.py (You MUST update this file!)

*v2.2.5:*
- Support for SEAnimType.Additive
- New utilities for selecting bones (All / Keyed)
- Annotations for all commands
- Updated 'Merge' command to it's proper name, 'Blend'

*v2.2.4:*
- Workaround for notetrack names that share Maya reserved keywords

*v2.2.3:*
- Ensure that we have at least 1 frame when loading

*v2.2.2:*
- Ensure that we have at least 1 progress step when loading

*v2.2.1:*
- Added a manual reset scene button (Importing a new anim will still reset the scene like normal)

*v2.2:*
- Fixed an issue which messed up saving animations.
- Made SEAnimUndo persist between saving, allowing for importing again when re-opening a Maya scene.
- General curve fixes

*v2.1.5:*
- Attempts to reset the rotations when binding gun to hands

*v2.1.4:*
- Catched an error that would happen when importing several animations

*v2.1.2:*
- Fixed a slight rotation issue

*v2.1.1:*
- Fixed an issue with Maya 2012 animation resetting
- Fixed plugin changing angle units

*v2.1:*
- Added support for merging (combining) animations on import via `SE Tools->Import and Merge`
- Better support for undoing the scene, smoother, faster
- Better error handling

*v2.0.3:*
- Bug fix for new scenes and old animation caches

*v2.0.2:*
- Better error logging

*v2.0.1:*
- Changed a few names to avoid a stupid Maya cache issue

*v2.0:*
- NOTICE: New install method, please completely remove the old `SETools` from scripts / usersetup.mel then follow the new install instructions!
- Rewrite of import system
- About 5x faster on import
- Drag and drop enabled
- Anim merge support
- Destructor arrays
- Bug fixes

*v1.5.6:*
- Fix in seanim.py for scale export!

*v1.5.5:*
- Simplified import and export
- Fixed framerate and end scene time when exporting anims
- Fixed another bug on import
- Added place notetrack feature
- Cleaned up codebase
- Added support for bone scale keys
- Exporting progress bar
- Ensured that the scene is in se format units (CM)
- Requires updated seanim.py!
