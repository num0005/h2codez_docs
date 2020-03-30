title:      JMA File Spec
desc:       Layout for the JMA file used to import animations.
template:   document
nav:        H2Tool>Animations>JMA File Spec
percent:    100
date:       2020/02/19
authors:    General_101

```markdown
<VERSION min = 16390, max = 16395>
<IF VERSION >= 16394<VERSION PART 2>  >
<FRAME COUNT min = 0, max = 2048>
<FPS>
<ACTOR COUNT min = 0, max = 30>
<ACTORS>
    <NAME maxlen = 32>
    <NODE COUNT min = 0, max = 256>
    <IF VERSION < 16394<NODE CHECKSUM>  >
    <NODES>
       <CONTROL STRING max=32>
       <IF VERSION == 16392|| 16393> <FIRST CHILD INDEX> <NEXT SIBLING INDEX>>
       <IF VERSION => 16394> <PARENT NODE INDEX>>
   </NODES>
   <FRAMES>
    <NODES FOR FAME>
        <FLOAT * 8>
    </NODES FOR FRAME>
   </FRAMES>
</ACTORS>
```
