title:      Blender Map Making 2.8
desc:       Notes on making maps with versions of Blender after 2.8
template:   document
nav:        Blender Tutorial>Map Making 2.8
percent:    100
date:       2019/9/30
authors:    General_101

[Halo Export Scripts](http://www.h2maps.net/Tools/PC/Export%20Scripts/Halo_Export.7z) -> Export scripts for your 3D modeling software of choice.

[Blender Program](https://www.blender.org/) -> The Blender modeling program itself.

[End Result](http://www.h2maps.net/Sources/H2EK%20Source/Manual/Blender/Tutorial2.8.blend) -> The end product of this tutorial for Blender for you to examine and compare.

[Spartan Model](http://www.h2maps.net/Sources/H2EK%20Source/Manual/Blender/Spartan.zip) -> Spartan model that should be to scale with the ingame player.

Hello!

My name is General_101 and welcome to my Halo 2 Blender tutorial. This is a guide for those who want to make functional Halo 2 maps with Blender. This guide will assume the reader has some basic idea on how to navigate the program.
We will begin by mimicking the map building section of the help tutorial that comes with the map editor but replacing terms used for 3DS Max with that of Blender.

Start Blender and you should see your Scene which should look something like this at start by default.

![](assets\2.8\1A.png)

This will be the space where we begin the work for our map in Blender. 
From here you can delete the cube by selecting it with LEFT MOUSE CLICK or selecting everything by hitting A and deselecting everything by hitting A twice rapidly on your keyboard then hitting X and selecting the prompt to delete.
If you do not want a cube then you can delete the object and select a new mesh from the add menu as seen here. 

![](assets\2.8\1B.png)

If you do add a mesh keep in mind that will be added wherever your 3D cursor is on your scene. 
If you want to recenter it then hit n to bring up the properties panel and zero location on the transform panel like so. Ensure that the properties panel is on the "item" tab

![](assets\2.8\1C.png)

![](assets\2.8\1D.png)

Let us start with a simple box map in this tutorial for simplicity's sake.

Begin by adding a cube mesh and a UV sphere to your scene. Make sure to center both of these objects in the properties panel though this isn't required for anything to work. 
Once you have added it set the scale of the cube to 100 on the x, y, and z. We want room for our players to fight in after all.

TIP: If have trouble seeing your complete mesh due to it not being rendered at a certain distance then change the clip distance. Open the properties panel by pressing N and switch to the "view" tab. Find a value labled "end" and change it to be a lot higher than 1000
000 like 99999 or something.

Your scene should now look something like this.

![](assets\2.8\1E.png)

Now that was have our basic level let us begin to create our frame node. The frame node is an object that is the origin of our map and should have all objects you want exported connected to it. 
Take great caution to ensure all objects you want exported are linked to the frame node or they will not be exported.
Take the UV sphere you created earlier and change the name of it by double clicking the current name sphere and rename it b_levelroot. 
The object must be named b_levelroot as this is the name of the object Halo 2 uses to orient the level. Not doing this properly will result in issues due to the script looking for an object with this name.
Make sure to not move your frame node after you start to setup your player and weapon spawns as this will lead to things being displaced.

TIP: One good way to check out a selection is to hit the zoom key. Simply hit "." on your keyboard and it will zoom in on whatever you have selected.

Now let us link the level to the frame node by making the frame node a parent of the level. 
Begin by selecting your cube then using SHIFT+LEFT MOUSE CLICK in the scene or simply click cube in the and then SHIFT+LEFT MOUSE CLICK in the object list.
Remember that...

![](assets\2.8\1F.png) = Parent

![](assets\2.8\1G.png) = Child

The last object selected will always be the parent.
Now hit the hotkey CTRL+P and select Object. Your steps should look something like this.

![](assets\2.8\1H.png)

![](assets\2.8\1I.png)

You should now notice that b_levelroot can be expanded to reveal the child which is our cube object by clicking the arrow pointing towards the parent object in the object list.
Let us select our cube and continue working on our level. If you were to somehow export the level now without errors the first thing you would notice is that textures do not appear on the correct side. 
This is because by default the normals are facing outwards on our mesh. 
To fix this we must flip the normals on the mesh so that we may see our textures properly ingame.

3DS Max Translated: Converting a mesh to an editable poly in 3DS Max is pretty much the same thing as selecting a mesh and going from object mode to edit mode.

Select your cube and change the interaction mode to edit mode. This will allow you to modify the faces of the cube individually and extensively. Make sure to also select face selection. This is what it should look like.

![](assets\2.8\1J.png)

One fantastic way to see which way normals are facing is to enable a little option in the overlays dropdown. Move your cursor down and select Display Face Normals As Lines. Change size to 30 to easily see the way normals are facing. This is what it should look like.

![](assets\2.8\1K.png)

Now your can press the hotkey A to select all or hit A twice rapidly to deselect all faces in an object. Select all and then go to Mesh -> Normals -> Recalculate Inside/Flip Normals. It should look like this.

![](assets\2.8\1L.png)

Notice that the normals that were pointing outwards are now pointing inwards.

![](assets\2.8\1M.png)

![](assets\2.8\1N.png)

Lets add materials for our level to use as textures. Go to the materials tab in Blender and add a new Material labeled "+sky". Under viewport display change the value labled "color" to a color that makes it stand out.
Create a second material and label it "f_im flat_light_scratchy" then give it a different color. Now select the +sky material and then select a face and hit assign. Assign the second material to the rest of the level. Look at this next image and compare to your scene.

![](assets\2.8\1O.png)


Now we have to unwrap our mesh so that we can change the size and location of the textures. Select your entire mesh by hitting A and then you have two ways to unwrap it. 
On a simple object like ours a simple Smart UV Project will do. 
On more complex shapes such as that of standard Halo maps we can use a mixture of marked seams and unwrap.
We will use Smart UV Project for now and the second method will be displayed after this. After you have selected your mesh then go down to Mesh->UV Unwrap-> Smart UV Project. The accompanying images will show you where.

![](assets\2.8\1P.png)

You will be greeted by a prompt box but the default options are fine for our current setup so just hit ok. Add a new window by right clicking on the part of the viewport that lets you resize the window. Choosing horizontal or vertical section will determine how the window gets cut.

![](assets\2.8\1Q.png)

A line should appear that follows where your cursor should be. Left clicking will cause it to confirm your selection and split the windows along that line.

![](assets\2.8\1R.png)

You should now have a second view

![](assets\2.8\1S.png)

and change the the editor to UV/Image Editor like in the following images.

![](assets\2.8\1T.png)

Now lets add a texture so we can more easily see what to expect ingame.

![](assets\2.8\1U.png)

This is the same texture we are using when we made the second material. Go ahead and save it and then apply it by going to your material and adding a texture file like so.
Go to the materials tab and select f_im flat_light_scratchy then go down to base color. At the end of the color picker there should be a small box with a circle. Click it and select "Image Texture", this should have added a file path with two new butons under it. Click open and browse for the image you downloaded before. 

![](assets\2.8\1V.png)

![](assets\2.8\1W.png)

![](assets\2.8\1X.png)

Add a new texture and then click open and select the texture you downloaded previously. Once your material has a texture then go into your UV editor and select the texture from there like so.

![](assets\2.8\1Y.png)

![](assets\2.8\1Z.png)

You can disable alpha in the image by pressing N in the UV viewport and setting the value labled "alpha" to none in the image tab.

Make sure to enable textures in viewport shading to see the texture. Should end up here. Switch to object mode to see the viewport shading first.

![](assets\2.8\11.png)

Ignore any faces that may display a texture that wasn't meant to be applied and focus on the faces that do have the material assigned as in the next image.

![](assets\2.8\12.png)

In the UV editor then select these faces by pressing A and then hit the hotkey S to scale and hotkey G to move the UV until the texture looks right to you. 
Ensure that you are in face selection mode in the UV editor as I will show you now.

![](assets\2.8\13.png)

One this is done you can then go to File->Export-Halo 2 asset. You should see no errors show up on the top right. Your ASS file should be ready and accepted by tool.