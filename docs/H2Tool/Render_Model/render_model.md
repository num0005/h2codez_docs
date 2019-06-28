title:      Render Model Tags
desc:       Making render_model tags.
template:   document
nav:        H2Tool>Render Model>Render Model
percent:    100
date:       2018/12/07
authors:    General_101

Render models are the tags for the object you see. The mesh of the object to be more exact. There are currently 3 methods for importing your own custom render models. 

There is the GBXmodel Upgrader. The purpose of this tool is to transfer data from a GBXmodel tag from CE to a render_model tag from Halo 2. 
While this generally works and can import rigged models it has many issues related to proper node location and can result in broken UVs. 

The second method is the one included in H2Codez which is a BSP conversion method. A model is first compiled as a BSP using ASS and then the data is transferred over to a render_model file. 
This should result in a model with intact UVs but is not meant for rigged models with more that one node. 

The third method is using a program named DAEConverter by Himanshu01. This program builds render_model tags using DAE files for the mesh data and can be rigged for new weapon models and such. 

The process for BSP conversion and DAE conversion will be outlined in the render_model docs. 