title:      Model Animation Graphs Tags
desc:       Describing model_animation_graphs tags
template:   document
nav:        H2Tool>Animations>Model Animation Graphs
percent:    100
date:       2020/03/29
authors:    General_101

Let us start by saying that you will need a preexisting model_animation_graph with the skeleton tag block filled in. Either reuse an existing one to add an animation to or modify the skeleton tag block manually to suit your needs.

Animation importing is now a feature H2Codez adds to the toolkit and this page will go over the process on getting import files for your animation needs. To begin this you will obviously need an animated model. Make sure you have 
the same skeleton setup in 3D editing software as you do in the model_animation_graph tag you plan on adding an animation file. Once you have finished an animation you wish to export you may then export the file.

| Name                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| JMA  - animation            | This is what a lot of animations will end up as. A default animation type that stores data necessary for movement. An example of this would be a walking animation. |
| JMM  - moving               | An animation type that is similar to JMA but leaves out redundant data that is not necessary for the cases it is used in. Examples are FP animations. |
| JMT  - rotation             | This animation type is an animation intended for turning animations Examples being how far chief can turn in a direction before he recenters himself. |
| JMO  - overlay              | This animation type like an additive animation, it adds movement to the base while keeping that movement intact. Example usage of overlay is a small hit animation that plays while you still want to keep a character able to perform it's running animation |
| JMR  - replacement          | This animation type removes the original animation for the nodes that are animated and plays it's own animation for it. An example for a replacement is a reload animation where you want to make sure the node positions are proper at each part of the reload. In that case you would only animate the upper body, so the lower parts can keep their original base animation that for instance still is a running animation |
| JMRX - replacement extended | No Idea |
| JMZ  - 3d animation         | This animation is basically what JMT was but for height instead of turning Examples being how chief turning up his body when looking up. |
| JMW  - world animation      | This animation type is a world relative animation. This means that the origin of the animation is the 0, 0, 0 location of the level. Example usage of this animation type would be a level designer animating a pelican dropoff for a mission. |

Be aware that the different extension types do have an affect on how the animation functions ingame. Each of them have a purpose and H2Tool will try to steer you in the right direction for what type you will need. 
The files themselves however have no differences besides extension. In order to export the animation use the cad_animationExporter_compact.mse script for 3DS Max and Blend2Halo2-Animation.py for Blender. 
Both of these files are found in the Halo_Export.7z in H2Tool Links to export the file. When this is done place it in a folder labeled "animations" like you would for collisions or physics. 
Remember that the name of the animation import file will be the name of the animation in the animation tag block. If you need the character ":" in the name such as "device:position" then use a space as spaces in the name are 
converted to ":". After the file is in then you can just use the animation checkbox in the launcher for compile or type the following command in CMD.

```markdown
h2tool append-animation (folder path)
```

Keep in mind that this only adds and if the name already exists then it won't overwrite it.

If you are at all aware with importing animations for CE then you should find most of this pretty similar.
