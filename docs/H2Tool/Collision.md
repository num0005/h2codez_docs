title:      Collision Tags
desc:       Preparing JMS files for importing with H2Tool to create working collision_model tags.
template:   document
nav:        H2Tool>Collision Tags
percent:    100
date:       2018/12/07
authors:    General_101

Collision tags in Halo 2 are created by exporting JMS files in UTF-16 format and making some specific changes to how the material and node names are done. We can then import the JMS file with H2Tool to get our working collision_model tags.
Let's get started by making the necessary changes to a freshly exported JMS file from either Blender or 3DS Max. Open it in Notepad++ and look to the first few lines that should look something like this
```markdown
8200
1
1
frame
-1
-1
0.000000	0.000000	0.000000	1.000000
0.000000	0.000000	0.000000
```
Add a "b_" before the name of the node in order to avoid an error related to whitespace.
```markdown
8200
1
1
b_frame
-1
-1
0.000000	0.000000	0.000000	1.000000
0.000000	0.000000	0.000000
```
Lets break down this section so that everything is clear.
```markdown
(JMS Version Number)
(Node List Checksum)
(Frame Count)
(Frame Name)
(Child Frame)
(Sibling Frame)
(I Rotation)	(J Rotation)	(K Rotation)	(W Rotation)
(X Translation)	(Y Translation)	(Z Translation)
```
Next we will solve an error related to the entire model being imported as one region and a material flag not making sense. You can fix this by changing <none> material from this....
```markdown
1
metal
<none>
0
1
unnamed
```
To this
```markdown
1
metal
base metal
0
2
base
metal
```
This changes the <none> to a permutation and a region in that order. It also adds the names of all the regions and permutations in one big list. Lets also break this list down for clarity.
```markdown
(Material Count)
(Material Name)
(Permutation) (Region)
(Marker Count)
(Name Count)
(Names of permutations and regions listed here)
```
The final step is to change the encoding. Open up the text file in Notepad++ and change the encoding from whatever it currently is to UCS-2 LE BOM. H2Tool should now accept your JMS files without issues assuming they are valid.