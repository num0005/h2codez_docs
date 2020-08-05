title:      Pathfinding
desc:       Abandon all hope ye who enter here.
template:   document
nav:        H2Tool>Pathfinding
percent:    100
date:       2020/02/19
authors:    General_101

THIS PART IS EXPERIMENTAL. DO NOT EXPECT ANYTHING TOO ADVANCED OR FOR STUFF TO WORK PROPERLY. LOTS OF RESEARCH IN THIS AREA IS STILL NEEDED.
{: .warning}

That being said a command has been added that may aid you in research or an attempt to make AI maps. The command goes by

```
pathfinding-from-coll (sbsp)
```
 
This is a WIP solution intended for meshes that have a custom collision mesh such as your custom level. Simply type out the command and type out the full path to the file in quotes. After the command is entered it will generate
a new scenario_structure_bsp in
 
```
C:\Users\(USERNAME)\Documents\Halo 2\tags
```
 
Example Usage:
```
pathfinding-from-coll "C:\Program Files (x86)\Microsoft Games\Halo 2 Map Editor\tags\01_bsp_0"
```
 
A file named (scenario)_import_setting.txt can be created in the directory that contains the .scenario file for the level that you wish to tweak the import settings for. (scenario) should be replaced for the name of the .scenario
file you are editing. So lockout_import_setting.txt for example. These are the following things that can be written into this file.

```markdown
[keep]
(sector index)
```

The first line will have "[keep]" and every line after that will be a listing of the surface index you want to keep the pathfinding sector for. The current pathfinding method will delete certain faces that are deemed unneeded.
Due to the nature of how new and experimental this is, this can be used when manual edits are needed for surfaces that may need sectors after all.

```markdown
[remove]
(sector index)
```

The next one is similar in setup but instead removes sectors that the pathfinding method did not remove that it perhaps should have.
What the surface index of something is can be found by using the collision_debug command in the H2Sapien console.

For the curious here is my understanding for the future.
[My Pathfinding Research](https://pastebin.com/XxZ9Mip5)
