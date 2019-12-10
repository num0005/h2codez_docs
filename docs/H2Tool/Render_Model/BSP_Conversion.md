title:      Render Model BSP
desc:       Making render_model tags through converted BSP geometry.
template:   document
nav:        H2Tool>Render Model>BSP Conversion
percent:    100
date:       2018/12/07
authors:    General_101

# Links
[Example files](http://www.h2maps.net/Sources/H2EK%20Source/Manual/BSPConverter/Example%20Render%20Model.7z) for the render model importing.

In order to import a working render model one must first export a valid ASS file. You will want to assign your shaders for the model somewhere in the shader_collection so that they are assigned to the BSP during compile.
This will help you later. A good method to prevent out of BSP errors is to surround your model in a box and give it a unique shader with the @ shader symbol at the end of the shader name. 
This will expand the space for the model as collision only meaning no render geometry is added to your render model. Give the rest of the model the ! shader symbol at the end of the material name so that it only generates 
render geometry  and the ) shader symbol to stop tool from welding vertices that are too close.This will help with errors related to collisions and such.
This won't solve everything due to the methods but this will help with most of your issues. 

You are now ready to use the render command. Hit the browse button and select the ASS file in your render folder. Select render in the model type and make sure the dropdown is on BSP.
Once it is compiled the result is ready to use unless you have more than one permutation or region. In this case you have to fix the result manually to complete it.
We will go over how to get it usable in Halo 2 now. Please download the render example pack so that you may follow along as I explain.

The command adds a dummy region and permutation for you that always points to section index 0 If you want multiple permutations you can change the section index to the represent the permutation you want. The first section you see being index 0 and the second in the list being index 1.

Now you may have read this and now be wondering how multiple sections for permutations work. It's pretty simple.

![](assets/BSPConversionStep9.png)

Simply place multiple ASS files in the same directory and they will be added as new sections. The order they are in alphabetically will determine the section order. From here simply reference the proper index in the permutation 
section.

Multiple LODs is also a very similar concept. Say you have 6 different models, each of them for an LOD section. You make six different ASS files and then each of them will be added as seperate sections much like with the permutation instructions.
This time however you take each section and give a unique index to each section under permutation like so.

![](assets/BSPConversionStep10.png)