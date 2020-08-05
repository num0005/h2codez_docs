title:      Misc H2Sapien Changes
desc:       Changes that seem important enough to mention but not important enough for their own file.
template:   document
nav:        H2Sapien>H2Sapien Misc
percent:    100
date:       2020/02/19
authors:    General_101

## New Instance
If you click file then you will see a new option labeled "New Instance". This will simply let you start a second instance from the file menu.
 
## Window
You will see a new option in the toolbar labeled "Window". It will has three options that you can use to organize the window panels.
"Cascade" brings all the windows diagonally on the screen. "Tile Horizontally" puts each window into one quadrant of the screen. Very useful to organize your windows easily. "Arrange Icons" seems to do nothing.
 
## Scenario Type
You could choose the scenario type before however the strings for the scenario type were commented out.
Click on the mission folder in "Hierarchy Pane" then you can change the type in the "Properties Palette". You can select your scenario type here and H2Tool will compile what you decide.
 
## Run Commands
Allows you to run commands from a new input box.
 
## New Commands
I will list new commands that can be typed into the H2Sapien console here.
 
set_temp render_pathfinding_debug (boolean)

    description: This command will enable or disable the display of the pathfinding mesh using a true or false
 
## Script Execution
Clicking this button in the scenario tab will make H2Sapien run your scripts so that you may see how they work. Some script functions will not work in H2Sapien and must be tested ingame like ai_place.
 
## Decorations
render_decorations (boolean)

    description: Render_decorations has been changed to do exactly as it should when enabled. Be aware that you will need to change H2Sapien to use ingame quality(High settings ingame) to actually see the decorators after this. Enable or disable with a 0/false or 1/true

## Baggage.txt
Baggage.txt is a txt file that was output upon hitting CTRL+Shift+B in H1Sapien. In H2Sapien this causes the program to crash.
With H2Codez the file will be properly written for you to view. This file can be used to view the amount of data a certain type of tag is taking up allowing you to easily see issues related to overflow.
 
## In-Game Display Settings
If you click the scenarios tab in H2Sapien it will reveal a new option in the drop down window called "In-Game Display Settings". This will change your H2Sapien display settings to more closely resemble the ingame options you have set in your Halo 2 copy. This will allow the modder to see things like environment maps and higher game view resolution in H2Sapien.

## Unit Playtest
Under the structure data folder there is a folder named Unit Playtest. Selecting this folder and right clicking will place the biped set to spawn from the first spawn index. So if a player has set the first spawn index to spawn a Dervish biped then unit playtest
will spawn the biped from the elite block index in globals. After placing it a player can press TAB to get a first person view from the biped they have placed. Using the keys "[" and "]" will switch between all the bipeds viewpoints that exist in the map. 
Once TAB is pressed the user can then press BACKSPACE to switch to first person then BACKSPACE again to switch to flycam and then BACKSPACE once more to switch to third person view.

## Missing Hierarchy Folders Readded
H2Sapien is missing various SP related options in the properties panel. The following folders have been readded to the H2Sapien menu through H2Codez.

	Bipeds
	Vehicles
	Weapons 
	Equipment
	Creatures
