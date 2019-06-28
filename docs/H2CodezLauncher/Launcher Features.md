title:      H2Codez Launcher
desc:       Launcher Features
template:   document
nav:        H2Codez Launcher>Features
percent:    100
date:       2018/12/07
authors:    General_101

## Shared Removal
Do not use this at the moment unless you understand what you are doing. Using this option will leave you with an unknown crash at time of writing.
{: .warning}

When a map is built H2Tool checks the assets of the map against a tag list for shared and then does not package the assets that exist while leaving a reference to shared in the scenario file. 
H2Codez has an option to ignore this and instead package all dependencies on your map into your map file. This can be used to overwrite default files such as a custom globals.globals which allows for custom bipeds and weapons. 

As a workaround until this is solved you can use the following link in order to have some more control over your map than you would previously.

[Edited Shared and Tags](https://mega.nz/#!Q0Mk2YzL!CLVagIOnZhS6zmFqn-HME5k6I_qcCsuRkh2s8QiGENE)

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
 
If the user has his selection on collision then it will search for a collision folder. If we have our path set to objects\multi\test then it will compile a JMS/JMSv2 file from objects\multi\test\collision.
Be warned that the outputted file will not be placed in its proper place and will instead be placed outside the destination folder. Just move it back in and it will be fine.
 
If the user has his selection on physics then it will search for a physics folder. If we have our path set to objects\multi\test then it will compile a JMSv2 file from objects\multi\test\physics. 
This one does get placed in its proper folder so you're done here.
 
If the user has his selection on render then the next action will depend upon the compile type chosen by the dropdown in the bottom left. If the user has his selection on render and BSP chosen in the bottom left drop down then it will search for a render folder.
If we have our path set to objects\multi\test then it will compile a ASS/JMS/JMSv2 file from objects\multi\test\render. This one does get placed in its proper folder. If the user has his selection on render and DAE chosen in the bottom left drop down then it we can ignore the previous template we setup as the file can be compiled from anywhere.
 
If the user has his selection on all or objects it will run through all of the above and create a model tag and link the results of the previous instructions if any. An object tag will also be created that links the model tag.
You can use the object type drop down to select an object type.