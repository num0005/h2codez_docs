title:      Physics Model Tags
desc:       Preparing JMS files for importing with H2Tool to create working physics_model tags.
template:   document
nav:        H2Tool>Physics Model Tags
percent:    100
date:       2018/12/07
authors:    General_101

Physics model files are a bit more tricky. You will need to do a couple of things to set these up properly so begin by exporting two files. 
Our regular JMS file using the regular exporter and a second JMS file using the "shitty" exporter. Take the JMSv2 template from [H2Tool Links](https://num0005.github.io/h2codez_docs/w/H2Tool/H2Tool_Links.html) and get ready to fill it in for your physics model. 
You will want to first fill out the node section. Go to your filled out JMS file and take the node from there. Should look something like this.
```markdown
1
frame
-1
-1
0.000000    0.000000    0.000000    1.000000
0.000000    0.000000    0.000000
```
Convert it to this and place it in your node list
```markdown
;### NODES ###
1
;   <name>
;   <parent node index>
;   <default rotation <i,j,k,w>>
;   <default translation <x,y,z>>
 
;NODE 0
b_frame
-1
0.0000000000    0.0000000000    0.0000000000    1.0000000000
0.0000000000    0.0000000000    0.0000000000
```
Notice how JMSv2 has 10 unit places instead of six unit places in the CE JMS file. This is actually important. H2Tool may have issues parsing the info if it does not use this length for the values. Just adding more zeros at the end will do.
Now you want to assign a material with a region and permutation. Begin by adding this to your template.
```markdown
;### MATERIALS ###
1
;   <name>
;   <material name>

;MATERIAL 0
(global material name)
(permutation) (region)
```
Physics don't use shaders for their material names. They instead use material effects. Pick something you like.
```markdown
;### MATERIALS ###
1
;   <name>
;   <material name>

;MATERIAL 0
hard_metal_thick_hum
base default
```
Now that you have your materials and nodes setup lets decide on what type of mesh we want for our physics file to be.
## Sphere
Lets say we want a sphere based collision. Lets fill out the sphere section in our JMS file. In order to figure out what radius our sphere will be you can create a UV sphere in Blender and scale it to what you want to cover the model.
Be sure that the scale is uniform since spheres only take radius. Now to get the radius of our sphere you will want to take the value of a dimension and divide it by half. This will give you the value for radius.
```markdown
;### SPHERES ###
0
;   <name of object>
;   <node index starting from 0>
;   <material index starting from 0>
;   <rotation <i,j,k,w>>
;   <translation <x,y,z>>
;   <radius>

;SPHERE 0
phy_test
0
0
0.0000000000    0.0000000000    0.0000000000    1.0000000000
0.0000000000    0.0000000000    0.0000000000
10
```
An example of what you should end up with.

## Box
A box is pretty simple. Go to Blender and make a cube shaped mesh. Form it until it covers the model you are attempting to make a physics model for. The scale doesn't have to be uniform for this. Once it is done take the dimensions
of the model and use the XYZ of the model as your XYZ for the JMS file.
```markdown
;### BOXES ###
1
;   <name>
;   <parent>
;   <material>
;   <rotation <i,j,k,w>>
;   <translation <x,y,z>>
;   <width (x)>
;   <length (y)>
;   <height (z)>

;BOX 0
phy_test
0
0
0.0000000000    0.0000000000    0.0000000000    1.0000000000
0.0000000000    0.0000000000    0.0000000000
10
10
10
```
## Capsules
Take a cylinder and keep the X and Y uniform. The Z can be changed however you want. Take the Z as height and take either the X or Y halved as your radius.
```markdown
;### CAPSULES ###
1
;   <name>
;   <parent>
;   <material>
;   <rotation <i,j,k,w>>
;   <translation <x,y,z>>
;   <height>
;   <radius>

;CAPSULE 0
phy_test
0
0
0.0000000000    0.0000000000    0.0000000000    1.0000000000
0.0000000000    0.0000000000    0.0000000000
10
10
```
## Convex
Use the "shitty" exporter for this part. You should see a vertice count along with a ton of vertice translation.
```markdown
20298
-25.17850097136 -10.93558594447 1.883197579523
-27.11733181272 -10.73211953932 2.356396971319
-24.86580137328 -8.290422677639 1.291731673068
11.59661842818  -23.82216938133 105.8638305997
14.97394742063  -22.87263726843 104.0894662136
11.97188461252  -24.29693543778 105.9821971142
-22.34400461455 -8.462422456568 104.3313659027
-21.94563845990 -9.118888279478 106.3428633173
-21.89797185450 -8.365689247566 117.0702828627
-26.99223197351 2.764929779565  11.34675208267
-23.67920289841 3.494695508262  6.549091582442
-23.61610297952 4.087728079370  6.548391583341
-13.79571560168 10.63251966734  40.68371437582
```
Should look like this. In order to use this data in our physics model we need to create a convex collision. Fill out this part of the template.
```markdown
;### CONVEX SHAPES ###
1
;   <name>
;   <parent>
;   <material>
;   <rotation <i,j,k,w>>
;   <translation <x,y,z>>
;   <vertex count>
;   <...vertices>

;CONVEX SHAPE 0
(object name)
0
0
0.0000000000    0.0000000000    0.0000000000    1.0000000000
0.0000000000    0.0000000000    0.0000000000
(vertice count)
(vertice list)
```
Create a convex shape entry in the list as ;CONVEX SHAPE # and give it a name. Parent is the index of the node you are referencing as it it is in the node list. So if l_thigh is the third node listed in your JMSv2 file then parent will be written as 3.
```markdown
(object name)
1
0
```
The material index will depend on what effect you want for that object. Again this is based on the order that it is listed in for the JMSv2 File. The next part is a bit annoying. Basically what this part is is the centroid of the object that you are exporting. 
So while frame is at 0 0 0 our physics object may bee 3 units above frame so you would type 0 0 3 for the physics object for it's placement in relation to frame. 
I personally change the location of frame to reflect location of the head of the bone the object is tied to then move frame to 0 0 0 with the object attached.
The final thing to do after this is formatting. Make sure that the files encoding is UCS-2 LE BOM. Ensure that all spaces are converted to tabs as spaces will cause H2Tool to freak out. The file should be ready after this.
You can use the tag extractor with extract import info to look at some of the physics_model.JMS files to get a good idea of what a JMSv2 file would want.