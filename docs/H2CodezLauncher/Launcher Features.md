title:      H2Codez Launcher
desc:       Launcher Features
template:   document
nav:        H2Codez Launcher>Features
percent:    100
date:       2020/02/19
authors:    General_101

## Shared Removal
Do not use this at the moment unless you understand what you are doing. Using this option will leave you with an unknown crash at time of writing.
{: .warning}

When a map is built H2Tool checks the assets of the map against a tag list for shared and then does not package the assets that exist while leaving a reference to shared in the scenario file. 
H2Codez has an option to ignore this and instead package all dependencies on your map into your map file. This can be used to overwrite default files such as a custom globals.globals which allows for custom bipeds and weapons. 

As a workaround until this is solved you can use the following link in order to have some more control over your map than you would previously.

[Edited Shared and Tags](http://www.h2maps.net/Sources/H2EK%20Source/Manual/Shared%20Removal%20Map%20+%20Tags.7z)

Download the linked zip and place the contents of this zip in your Halo 2 map editor folder. Backup anything it asks you to overwrite. This should allow you to have things like custom globals but keep in mind that this will blacklist your map unless
Halo 2 was patched to prevent that. It will also break map names, descriptions, and team options in the pregame lobby. People can use this map like any other custom map. They do not need the edited shared in this zip.

## Large Address Aware
This is an checkbox you can find in the settings menu of the H2 Toolkit Launcher. When checked the "Run H2Sapien" button and any H2Tool related buttons will run a version of the H2Tool/H2Sapien exes with the Large Address Aware flag enabled.
This will allow it to use up to four GBs of memory instead of the standard two. This can help with some crashes during H2Tool or H2Sapien running out of memory. Enable them at your own risk. 
Currently the only known bug is memory logging doesn't work properly but this should be stable to have on permanently with little issue.

## Reset H2Sapien Window Layout
An easy way to restore H2Sapien's window settings to default when the situation calls for something a bit more serious. This button found in the settings menu works by by deleting all the stored window size information found in "HKEY_CURRENT_USER/Software/bungie/sapien".
They should then be restored as if you had just installed H2Sapien.

## Open CMD In Toolkit Folder
Exactly as it says. Open a command prompt window to have access to H2Tool commands with some that may not be featured in the launcher for being misc or not working. Type H2Tool to begin typing commands the old fashioned way.

## Custom H2Tool Command
Same as above but run it directly from the launcher instead. Know exactly what you need to type in already? Just use this and cut out the H2Tool part. You can just type things like bitmaps scenarios/multi/example/bitmaps and begin.

## Model Compile
This should be pretty simple. This is the menu where you will find everything you need to compile your H2 models. Let us begin with a couple of examples.
 
If the user has his selection on collision then it will search for a collision folder. If we have our path set to objects\multi\test then it will compile a JMS file from objects\multi\test\collision.
 
If the user has his selection on physics then it will search for a physics folder. If we have our path set to objects\multi\test then it will compile a JMS file from objects\multi\test\physics. 
 
If the user has his selection on render then the next action will depend upon the compile type chosen by the dropdown in the bottom left. If the user has his selection on render and BSP chosen in the bottom left drop down then it will search for a render folder.
If we have our path set to objects\multi\test then it will compile a ASS/JMS file from objects\multi\test\render. This one does get placed in its proper folder. If the user has his selection on render and DAE chosen in the bottom left drop down then it we can ignore the previous template we setup as the file can be compiled from anywhere.

If the user has his selection on animations then it will search for a animations folder. If we have our path set to objects\multi\test then it will compile a JMA file from objects\multi\test\animations. 

If the user has his selection on all or objects it will run through all of the above and create a model tag and link the results of the previous instructions if any. An object tag will also be created that links the model tag.
You can use the object type drop down to select an object type.

## ALT Key
Holding the ALT key while pressing any browse button in the launcher and having no path in the text box will start you in the root of the Halo 2 folder in documents instead of the root of your Halo 2 map editor folder.
This will also switch the package function to cut the result instead of copying it to your custom maps folder

## Lipsync Compile
Using this option from the compile sound will allow you to append lipsync data to a compiled .sound tag. The lipsync command takes .LTF files exported from the program Impersonator. Reference the .wav file in the sound path
text box and the .LTF in the lipsync text box. The .wav file path will be used to get the path to where it would have been outputted in the tags folder.

## Repair Registry
This option in settings will check your registry to see if the proper keys for running Guerrilla and the launcher.

## Set Permissions
This option in settings will clear the permissions on your Halo 2 Map Editor folder and the files inside of it and leave an everyone permissions with full access. This will allow you to run the tools without admin and save
files in the folder properly.

## Language
This option in settings will change the launcher dialog to one of the available choices. System locale will use your default OS language if it's available as an option. Otherwise it can be manually set.

## Ignore Updates
This option in settings will let you ignore updates for launcher and H2Codez. You scoundrel!
