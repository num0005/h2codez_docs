title:      Blender Map Making 2.79
desc:       Notes on making maps with versions of Blender before 2.8
template:   document
nav:        Blender Tutorial>Map Making 2.79
percent:    100
date:       2019/9/30
authors:    General_101

[Halo Export Scripts](http://www.h2maps.net/Tools/PC/Export%20Scripts/Halo_Export.7z) -> Export scripts for your 3D modeling software of choice.

[Blender Program](https://www.blender.org/) -> The Blender modeling program itself.

[End Result](https://mega.nz/#!oodATZiI!cmQx44g8ghK2XOts8qHo-iDYcwydiIKBRZqW4_RM19s) -> The end product of this tutorial for Blender for you to examine and compare.

[Spartan Model](https://mega.nz/#!Fo0kRBwL!RHAZkPfnt0oTa0bmHO1Y_it1hltZqaG8wp0LIaz5aeg) -> Spartan model that should be to scale with the ingame player.
 
Hello!
 
My name is General_101 and welcome to my Halo 2 Blender tutorial. This is a guide for those who want to make functional Halo 2 maps with Blender. This guide will assume the reader has some basic idea on how to navigate the program.
We will begin by mimicking the map building section of the help tutorial that comes with the map editor but replacing terms used for 3DS Max with that of blender.
 
Start Blender and you should see your Scene which should look something like this at start by default.
 
![](assets\2.79\1A.png)
 
This will be the space where we begin the work for our map in Blender.
From here you can delete the cube by selecting it with RIGHT MOUSE CLICK or deselecting/selecting everything by hitting A on your keyboard then hitting X and selecting the prompt to delete.
If you do not want a cube then you can delete the object and select a new mesh from the add menu as seen here.
 
![](assets\2.79\1B.png)
 
If you do add a mesh keep in mind that will be added wherever your 3D cursor is on your scene.
If you want to recenter it then hit n to bring up the properties panel and zero location on the transform panel like so.
 
![](assets\2.79\1C.png)
 
![](assets\2.79\1D.png)
 
Let us start with a simple box map in this tutorial for simplicity's sake.
 
Begin by adding a cube mesh and a UV sphere to your scene. Make sure to center both of these objects in the properties panel.
Once you have added it set the scale of the cube to 100 on the x, y, and z. We want room for our players to fight in after all.
 
TIP: If have trouble seeing your complete mesh due to it not being rendered at a certain distance then change the clip distance. Scroll down in your properties panel and find clip then change end to be a lot higher than 1000
000 like 99999 or something.
 
Your scene should now look something like this.
 
![](assets\2.79\1E.png)
 
Now that was have our basic level let us begin to create our frame node. The frame node is an object that is the origin of our map and should have all objects you want exported connected to it.
Take great caution to ensure all objects you want exported are linked to the frame node or they will not be exported.
Take the UV sphere you created earlier and change the name of it by double clicking the current name sphere and rename it b_levelroot.
The object must be named b_levelroot as this is the name of the object Halo 2 uses to orient the level. Not doing this properly will result in issues.
Make sure to not move your frame node after you start to setup your player and weapon spawns as this could lead to things being displaced.
 
TIP: One good way to check out a selection is to hit the zoom key. Simply hit . on your keyboard and it will zoom in on whatever you have selected.
 
Now let us link the level to the frame node by making the frame node a parent of the level.
Begin by selecting your cube then using SHIFT+RIGHT MOUSE CLICK in the scene or simply click cube in the and then SHIFT+LEFT MOUSE CLICK in the outliner.
Remember that...
Orange with white text = Parent
Orange with black text = Child
The last object selected will always be the parent.
Now hit the hotkey CTRL+P and select Object. Your steps should look something like this.
 
![](assets\2.79\1F.png)
 
![](assets\2.79\1G.png)
 
You should now notice that b_levelroot can be expanded to reveal the child which is our cube object.
Let us select our cube and continue working on our level. If you were to somehow export the level now without errors the first thing you would notice is that textures do not appear.
This is because by default the normals are facing outwards on our mesh.
To fix this we must flip the normals on the mesh so that we may see our textures properly ingame.
 
3DS Max Translated: Converting a mesh to an editable poly in 3DS Max is pretty much the same thing as selecting a mesh and going from object mode to edit mode.
 
Select your cube and change the interaction mode to edit mode. This will allow you to modify the faces of the cube individually and extensively. Make sure to also select face selection. This is what it should look like.
 
![](assets\2.79\1H.png)
 
One fantastic way to see which way normals are facing is to enable a little option in the properties window. Scroll down and select Display Face Normals As Lines. Change size to 1 to easily see the way normals are facing. This is what it should look like.
 
![](assets\2.79\1I.png)
 
Now your can press the hotkey A to deselect or select all faces in an object. Select all and then go to Mesh -> Normals -> Recalculate Inside/Flip Normals. It should look like this.
 
![](assets\2.79\1J.png)
 
![](assets\2.79\1K.png)
 
![](assets\2.79\1M.png)
 
Lets add materials for our level to use as textures. Go to the materials tab in Blender and add a new Material labeled "+sky" Change the diffuse of it to a color that makes it stand out.
Create a second material and label it "f_im flat_light_scratchy" then give it a different diffuse color. Now select the +sky material and then select a face and hit assign. Assign the second material to the rest of the level. Look at this next image and compare to your scene.
 
![](assets\2.79\1N.png)
 
 
Now we have to unwrap our mesh so that we can change the size and location of the textures. Select your entire mesh by hitting A and then you have two ways to unwrap it.
On a simple object like ours a simple Smart UV Project will do.
On more complex shapes such as that of standard Halo maps we can use a mixture of marked seams and unwrap.
We will use Smart UV Project for now and the second method will be displayed after this. After you have selected your mesh then go down to Mesh->UV Unwrap-> Smart UV Project. The accompanying images will show you where.
 
![](assets\2.79\1O.png)
 
You will be greeted by a prompt box but the default options are fine for our current setup so just hit ok. Add a new window and change the the editor to UV/Image Editor like in the following images.
 
![](assets\2.79\1P.png)
 
![](assets\2.79\1Q.png)
 
Now lets add a texture so we can more easily see what to expect ingame.
 
![](assets\2.79\1R.png)
 
This is the same texture we are calling when we made the second material. Go ahead and save it and then apply it by going to your material and adding a texture file like so.
Go to the materials tab and select f_im flat_light_scratchy then go into the textures tab.
 
![](assets\2.79\1S.png)
 
![](assets\2.79\1T.png)
 
Add a new texture and then click open and select the texture you downloaded previously. Once your material has a texture then go into your UV editor and select the texture from there like so.
 
![](assets\2.79\1U.png)
 
Make sure to enable textured solid in the properties panel under shading in your 3D editor to see the texture. Should end up here.
 
![](assets\2.79\1V.png)
 
Ignore any faces that may display a texture that wasn't meant to be applied and focus on the faces that do have the material assigned as in the next image.
 
![](assets\2.79\1W.png)
 
In the UV editor then select these faces and then hit the hotkey S to scale and hotkey G to move the UV until the texture looks right to you.
Ensure that you are in face selection mode in the UV editor as I will show you now.
 
![](assets\2.79\1X.png)
 
Now if this was 3DS Max you would be about ready to export the final product. This is Blender though and a few extra steps must be taken. These are crucial for the map to export properly so follow them closely.
Let use first zoom in on our b_levelroot using the hotkey . to zoom in.
Every single object you make in Blender must have its faces be converted to triangles. This is important as the exporter and Halo 2 will not accept it otherwise. Select your b_levelroot and go into edit mode then hit hotkey A to ensure it selects all.
Go to Mesh->Faces->Triangulate Faces. Your UV sphere should be made out of triangles now.
 
![](assets\2.79\1Y.png)
 
Every single object must also be unwrapped including the b_levelroot mesh. Simply select all faces and hit Smart UV Unwrap. This is all you have to do for the b_levelroot to be done with UVs.
All objects including the b_levelroot must have a material even if it has no texture. Add a new material to the b_levelroot and assign it. This is all you have to do here.
The final result should look something like this. Disable textures solids to see diffuse again.
 
![](assets\2.79\1Z.png)
 
Do the same for all other objects in the scene. One this is done you can then go to File->Export-Halo 2 asset. You should see no errors show up on the top right. Your ASS file should be ready and accepted by tool.