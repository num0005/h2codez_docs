title:      Blender Instance Geo 2.79
desc:       Notes on making instance geometry with versions of Blender before 2.8
template:   document
nav:        Blender Tutorial>Instance Geo 2.79
percent:    100
date:       2020/02/19
authors:    General_101

[Halo Export Scripts](http://www.h2maps.net/Tools/PC/Export%20Scripts/Halo_Export.7z) -> Export scripts for your 3D modeling software of choice.

[Blender Program](https://www.blender.org/) -> The Blender modeling program itself.

[End Result of First Tutorial](http://www.h2maps.net/Sources/H2EK%20Source/Manual/Blender/Tutorial.blend) -> The end product of the first tutorial for Blender for you to examine and compare.

[End Result](http://www.h2maps.net/Sources/H2EK%20Source/Manual/Blender/Tutorial2.blend) -> The end product of the this tutorial for Blender for you to examine and compare.

[Spartan Model](http://www.h2maps.net/Sources/H2EK%20Source/Manual/Blender/Spartan.zip) -> Spartan model that should be to scale with the ingame player.

Hi again and welcome to my second tutorial on working with the Halo 2 Blender exporter. 
In this tutorial we are going to cover how to use instance geometry in Blender for Halo 2. This guide assumes you have followed the first part.
If you have not done the first part of this tutorial then get the tutorial map linked in the above. Let us briefly explain what instance geometry is and how it can benefit you.

Instance geometry is repeating geometry that can be used to make copies of an object at little cost in memory compared to making unique objects.
While any edits you make to the object in edit mode will be cloned to all other instances you can change scale, rotation, and translation in object mode to make them appear unique or to just place them where appropriate.
Keep in mind that while rotation and translation can be changed to your heart's content scaling must remain uniform. This means that on object with a scale of 2 on the x axis must also be 2 on the y and z axis.
In this case a unique object would have information stored that tells us about the objects faces while an instance would just copy that data from the linked object.
Instance geometry is very useful not only for its memory saving capabilities but also due to the fact that we do not need to make these objects a part of the level.

Let use begin by taking the map we made previously and make some edits to it. You can download it from the link above if you wish to skip over to this tutorial.
Add a mesh to the scene. It can be whatever you want but just make sure it is a separate object that is linked to that b_levelroot much like your cube from before. 
Remember to take your new object and do the same steps you did to the cube in the last tutorial. We first take our object and triangulate the faces. Once that is done we then give our object a material and UV unwrap it.
You are now ready to name your object. Halo 2 tool recognizes that we are giving it an instance object by using the % prefix. This will tell tool what we want it to do with our mesh when we compile our map.
To properly name instance geo with our exporter we need to follow a certain setup.
The first step is to ensure the object is linked to the b_levelroot
The second step is to make sure your object is properly sealed as it will still make tool put out open edge errors and such if it is not properly made.
Your third and final step is to then name the object properly. The naming of instance geo starts with the % and your object name. Our object will be called spire so it will become %spire.
Your scene should look something like this.

![](assets\2.79\2A.png)

Now we want multiple copies of this mesh all over our map so let us create linked duplicates of our object. Go into object mode and select your %spire object then hit duplicate linked. You will now get a cloned object and you will notice that when you go into edit mode that it selects both of the objects.
Any changes you make to either of them will be transferred across all instances in your scene. If you have already made a duplicate of an object without linking them then you can do this by first selecting the object you want to turn into an instance and the object you want to link it to.
When this is done press the hotkey CTRL+L and then select object data. Go ahead and spend some time placing instance objects around your map.
Now that you have finished placing your instance geometry you should properly name them. Our first object was named %spire and all of our instances must now be called %spirexx with x representing an arrangement of numbers.
For recap you start by naming an object %(Object name) and calling the instances %(Object name used previously)xx. You should start with 01 and then go from there.
When you are done it should look like this image.

![](assets\2.79\2B.png)

Your work here is done. You can now use this knowledge to create instance geometry for your Halo 2 maps. You can move on for now but this last section will show you the benefits of such methods. I have exported to files here.
One has instance geometry properly set up and the other does not. They are named tutorial and tutorial20 respectably. While not a huge difference due to the simplicity of our map you can already see the difference in the exported ASS files.
Tutorial which is our ASS file with instance geometry properly setups comes out at 374 KB on disk while Tutorial20 with the objects we added not being made into proper instance objects comes out at 551 KB on disk. One can already imagine the space one can save using tools such as these.

This is it for the tutorial. Keep on mapping for The Great Journey.
