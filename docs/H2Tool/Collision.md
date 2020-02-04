title:      Collision Tags
desc:       Preparing JMS files for importing with H2Tool to create working collision_model tags.
template:   document
nav:        H2Tool>Collision Tags
percent:    100
date:       2020/2/04
authors:    General_101

Be warned that when you generate a new collision tag that it will be placed outside of the parent directory. Move it back in afterwards.
{: .warning}

[Halo Export Scripts](http://www.h2maps.net/Tools/PC/Export%20Scripts/Halo_Export.7z) -> Export scripts for your 3D modeling software of choice.

[Blender Program](https://www.blender.org/) -> The Blender modeling program itself.

Collision tags in Halo 2 are created by exporting JMS files in UTF-16 format. We can then import the JMS file with H2Tool to get our working collision_model tags.

Start by installing the Blend2Halo2-JMSv2.py script found in the Halo_Export.7z archive to be able to export valid JMS files for Halo 2. This script should do what you need for rigged meshes.

Once you have that script go to your Blender scene and add an armature object. Leave it named Armature as the script specifically looks for an object named this at the moment. Add the amount of bones you need from here.
Create the mesh and morph untill you have the collision shape you need. Be aware that collisions should be simple and use fewer polys when compared to a render_model. You want as few as possible for memory reasons.
Once the mesh is modeled you can use weight paint to define what parts belong to what node. Make sure that each seperate piece is only rigged to a single node. Collisions do not take skinned meshes so seperate your collision in
chunks and weight each piece at maximum strength for that node. Once this is done you should be able to export the collision and import it for H2Tool

Place the JMS file inside a folder labeled "collision" and browse the the parent folder that you created the collision folder in using the launcher. Hit compile while having collisions checkmarked.