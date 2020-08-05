title:      Misc H2Tool Changes
desc:       Changes that seem important enough to mention but not important enough for their own file.
template:   document
nav:        H2Tool>H2Tool Misc
percent:    100
date:       2020/02/19
authors:    General_101

## Unlocked Scenario Compiling
By default H2Tool does not allow any other scenario type than multiplayer to be built. H2Codez allows you to package cache files using different scenario types like singeplayer, shared, single player shared, and mainmenu.

## AI Script Functions
Scripts with AI commands will now function as intended as long as the user follows the proper instructions.

```
(ai_place wave1)
```

Using names here for ai_place will work as intended however if the user wanted to reference starting location then they would have to use something like this.

```
(ai_place wave1/0)
```

With wave1 being the name of the squad and 0 being the tag block index of starting location. This may change in the future so that most of the AI commands if not all use names instead of index.
List of which work with which is here.

- AI behavior
- Conversation
- AI orders
- AI (starting locations referenced by block index)
- Style (internal ID only)
- Navpoint (internal ID only)
- AI command list (internal ID only)
- HUD message (internal ID only)
- Point reference
- cs_movement_mode
- ai_combat_status

Restored Globals List

cs_movement_mode            

	813_global 0 ai_movement_patrol
	
	815_global 2 ai_movement_combat

	816_global 3 ai_movement_flee

ai_combat_status

	803_global 0 ai_combat_status_certain

	804_global 1 ai_combat_status_idle
	
	805_global 2 ai_combat_status_alert

	806_global 3 ai_combat_status_active

	807_global 4 ai_combat_status_uninspected
	
	808_global 5 ai_combat_status_definite
	
	810_global 7 ai_combat_status_visible
	
	811_global 8 ai_combat_status_clear_los
	
	812_global 9 ai_combat_status_dangerous

## Increase BSP max depth
A passive change to H2tool's level compiler that allows for more detailed geometry to be imported. Increased to a maximum value of 512.

## Dump as XML command
The command "dump-as-xml (tag_path)" was added to H2Tool to allow you to dump the values in a tag as an XML document. This can help you compare two tags quickly and efficiently using something like the compare feature in Notepad++.

## Fix extracted lightmaps command
THIS PART IS EXPERIMENTAL. YOU MAY STILL EXPERIENCE CRASHES WHILE ATTEMPTING TO RELIGHT THE MAP EVEN AFTER THIS IS DONE.
{: .warning}

The command "fix-extracted-lightmaps (scenario_path)" will take the cluster blocks from SBSP and copy it over to the lightmap cluster block. This will let you relight extracted maps.

## Multi language strings
Creating a folder called data_(language code) and placing an identical path for a text file will compile both an English string from data and an additional string from the newly created data_(language code) folder you created.
You can use this to add multi language support to your string tags. See the markdown below for details on the language codes available. 

```markdown
jpn
de
fr
sp
it
kor
cht
pt
```
