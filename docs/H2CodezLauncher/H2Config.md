title:      H2Codez Settings
desc:       H2Codes config description
template:   document
nav:        H2Codez Launcher>Config
percent:    100
date:       2018/12/07
authors:    General_101

A new feature for H2Codez is upon the starting and closing of H2EK a file named "H2Codez.conf" will be created in the root directory of the map editor.
There will be a few options inside that we will go over here. Make sure to close everything related to the tool kit before editing.
 
#####discord_enabled = X

Enable or disable Discord Rich Presence with a true or false. To be or not to be stalked?
 
#####expert_mode = X

Enable or disable expert mode on startup for H2Sapien with a true or false. Having it enabled will let you do things like manually edit object ID.
 
#####in_game_lod = X

Is just the config option for the "In-Game Display Settings" option in the scenario drop down window. True or false to do as you wish on startup.
 
#####running_game_scripts = X

Is just the config option for the "Script Execution" option in the scenario drop down window. True or false to do as you wish on startup.
 
#####AllowVsync = X

Enable or disable Vsync with a true or false.
 
#####VideoMemory = X

The amount of video memory you have with the default value written being 100 MB. See your GPUs Vram and write the amount in MB here.
 
#####use_hardware_vertexprocessing = X

Use your GPU to help process the ingame view with a true or false here.
 
#####CinematicShadow = X

Who's that Pokemon? No seriously what the fuck does this do? Enable or disable with a true or false.
 
#####console_history_size = X

Will increase the amount of inputted commands that can be reused from the command history by pressing the UP ARROW.
 
#####decoration_force_update = X

Decorations in H2Sapien will not update when placed until the renderer is reset. This updates it the moment it is placed down for instant visuals but it will result in stutter. Enable or disable with a true or false.
 
#####disable_templete_view = X

Whether or not to have things like the simple shader template you are used to or just the tag blocks that include meta. Enable or disable with a true or false.
 
#####dump_screen_print_to_console = X

prints the results of the H2Sapien console to debug_console if enabled. Enable or disable with a true or false.
 
#####dump_tags_packaging = X

If true this will dump the processed scenario tag before packing it into the .map file. Was used for testing and comparisons between extracted and unpackaged scenario tags. Enable with a true or false.
 
#####enable_debug_console = X

A debug console for the toolkit in command prompt. Don't expect much. Enable or disable with a true or false.
 
#####experimental_tag_sync = X

THIS MAY RESULT IN CRASHES IF YOU EDIT CERTAIN THINGS SUCH AS CHANGING THE NODE SETUP OF A MODEL.
{: .warning}

A feature brought up in presentations of Halo 2 Xbox but left disabled in the shipped build of H2EK. As you may speculate from the name, this feature will update almost any edit you make to your tags in H2Guerilla to show in H2Sapien.
With this you can do things like shader editing in real time or edit effects. Enable or disable with a true or false.
 
#####patches_enabled = X

Disable H2Codez pretty much. Enable or disable with a true or false.
 
#####pathfinding_keep_angle_range = (0.0-360.0)

Surfaces that exceed this range will be removed in the pathfinding mesh when using the command pathfinding-from-coll.
 
#####render_pathfinding_debug = X

Render the pathfinding mesh in H2Sapien using this command. Enable or disable with a true or false.
 
#####show_hidden_fields = X

This will show or not show the normally hidden tag blocks from H2Guerilla like the release version. Enable or disable with a true or false.
 
#####simulate_game = X

Will make H2Sapien act as if it is running an actual instance of the game such as checkpoints as other tomfoolery. Enable or disable with a true or false.
 
#####use_loading_animation = X

You ask me why and I say why not. Enable with a true or false in the H2Codez.conf to see or not see the default H2 loading animation while loading maps in H2Sapien.

#####nvidia_fix = X
Changes the process name of H2Sapien to solve a graphical issue on some Nvidia cards. Enable or disable with a true or false.

#####enable_cache_writer_patches = X
Enables patches meant to edit how H2tool writes out the cache file data. Pretty much only related to cache_file_alignment at the moment. Enable or disable with a true or false.

#####disable_debug_tag_names = X
Don't add tag names to the cache file. Enable or disable with a true or false.

#####disable_sound_references_postprocessing = X

This may cause your map to get blacklisted from the custom maps list due to a large amount of tags. Do not use this unless Halo2.exe has been patched for this.
{: .warning}

Add all sounds to the cache file instead of just certain sounds of a certain vocalization type for MP cache files.

#####cache_file_alignment = (value)

Value needs to be multiples of 512 in order to not be blacklisted.
{: .warning}

Changes the layout of the data. Really more of a proof of concept than anything else. Value starts from 0 and goes up in multiples of 512 if you want to avoid issues.

#####fixup_extracted_bitmaps = X
Repair extracted bitmaps on package. Enable or disable with a true or false.
