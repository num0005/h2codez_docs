title:      Animations
desc:       Preparing animation import files for H2Tool to add new animations blocks to existing model_animation_graph. (for now)
template:   document
nav:        H2Tool>Animations
percent:    100
date:       2018/12/07
authors:    General_101

Let us start by saying that you will need a preexisting model_animation_graph with the skeleton tag block filled in. Either reuse an existing one to add an animation to or modify the skeleton tag block manually to suit your needs.

Animation importing is now a feature H2Codez adds to the toolkit and this page will go over the process on getting import files for your animation needs. To begin this you will obviously need an animated model. Make sure you have 
the same skeleton setup in 3D editing software as you do in the model_animation_graph tag you plan on adding an animation file. I will not be going over how to do this part as this is outside the area of my expertise but be aware 
that any CE or any general animation tutorial for 3DS Max will give you what you need to get here. Once you have finished an animation you wish to export you may then export the file.

jma     - animation

jmm     - moving

jmt     - rotation

jmo     - overlay

jmr     - replacement

jmrx    - replacement extended

jmz     - 3d animation

jmw     - world animation

Be aware that the different extension types do have an affect on how the animation functions ingame. Each of them have a purpose and H2Tool will try to steer you in the right direction for what type you will need. If you need a 
different type to please H2Tool then reexport the file instead of just changing the extension. There are some differences in how each of them are exported. In order to export the animation use the cad_animationExporter_compact.mse
script found in the Halo_Export.7z in H2Tool Links to export the file. Once you have the file go ahead an edit it in notepad++ and change the encoding to "UCS-2 LE BOM". When this is done place it in a folder labled "animations" 
like you would for collisions or physics. Remember that the name of the animation import file will be the name of the animation in the animation tag block. If you need the character ":" in the name such as "device:position" then 
use a space as spaces in the name are converted to ":". After the file is in then you can just use the animation checkbox in the launcher for compile or type the following command in CMD.

"h2tool append-animation (folder path)" 

Keep in mind that this only adds and if the name already exists then it won't overwrite it.

If you are at all aware with importing animations for CE then you should find most of this pretty similar.