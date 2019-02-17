title:      Multi Instance Lightmapper
desc:       Using multiple instances of the lightmapper to cut down on rasterizing time.
template:   document
nav:        H2Tool>Lightmapper
percent:    100
date:       2019/2/10
authors:    General_101
            num005

Lightmapping in Halo 2 by default is a bit of a pain. Some maps you make could take days to finish on Super. This make expansive maps with many different light sources be almost impossible to test quickly without doing tricks like
cutting out the BSP you are testing or using lower quality lightmaps. At the time of current writing the lightmapper farm technique used during the development of Halo 2 has been brought back to a usable state. Here is how to use it.

Limit the max number of lightmapping instances on one PC to the number of threads it supports for best performance. Leave one thread free if you want to use your PC for anything else during lightmapping.
{: .tip}

## Getting started

If you already know how to use the lightmaps command you can skip this part. Grab the scenario path and BSP name then choose your lightmap quality. Your choice is the following from lowest to highest.

- checkerboard
- direct_only
- draft_low
- draft_medium
- draft_high
- low
- medium
- high
- super

Both scenario path and BSP name don't include the file extension. 
{: .warning}

Make sure you don't have duplicate BSPs between your tags folder in program files and your tags folder in documents. Duplicates will cause your lightmaps to be unusable.
{: .warning}

## Automatic

Automatic doesn't support all the things possible with manual but it's a lot easier to use and is recommended for anyone that just wants to lightmap faster.

Begin by typing in the following command and set instance count to the number of instances you want it to start

```
h2tool lightmaps-local-multi-process (scenario path) (BSP name) (lightmapper quality) (instance count)
```
Once you run the command you should see it start a few tool instances and tell you it's waiting for them to exit, at this point you just wait.

Instance count can't be less than 2 as that doesn't make sense.
{: .tip}

Make sure you have enough free memory for all the tool instances you are running before you start
{: .warning}


## Manual

This is the more complex method but it's the only one that allows you to use all the features Bungie could.

Begin by typing in the following command

```
h2tool lightmaps-slave (scenario path) (BSP name) (lightmapper quality) (instance count) (instance index)
```


The instance count is how many instances of tool you want splitting the work starting at 0. Choose a number.

Now here is the most important part. The instance index of the command. If you typed an instance count of 3 then you want to type the command 3 times with an instance index for each value. Here is what this would look like.

```
h2tool lightmaps-slave scenarios\multi\halo\coagulation\coagulation coagulation medium 3 0

h2tool lightmaps-slave scenarios\multi\halo\coagulation\coagulation coagulation medium 3 1

h2tool lightmaps-slave scenarios\multi\halo\coagulation\coagulation coagulation medium 3 2
```
You should now have 3 tool windows each denoted with an index in the title name of the program. After these are all done it should have generated files labeled
 
```
(scenario name)_(BSP name)_lightmap_radiance_bitmaps_(#).bitmap.
```

Now it's time to merge them all using the following command.

```
h2tool lightmaps-master (scenario path) (BSP name) (lightmapper quality) (instance count)
```

You want to have the instance count match the number you ran previously otherwise you will get an incomplete lightmap bitmap. Here is an example of what it looks like completed.

```
h2tool lightmaps-master scenarios\multi\halo\coagulation\coagulation coagulation medium 3 
```

## Fork/clone (experimental)

#### Technical background

The lightmapping process on all instances/slaves is largely the same up to the rasterizing stage at which different instances generate radiance bitmaps for different parts of the BSP. This results in a lot of redundant processing if multiple instances are run on one system. This is an attempt to work around that by creating "clones" or "forks" of an initial lightmapping process when it reaches the rasterizing stage. It's quite unstable as cloning a process isn't officially supported on windows.

### Usage

Largely the same as manual but you only run two commands. See that section for more detail.

1.
```
h2tool lightmaps-slave-fork (scenario path) (BSP name) (lightmapper quality) (instance count)
```

2.
```
h2tool lightmaps-master (scenario path) (BSP name) (lightmapper quality) (instance count)
```

This is an unstable method and may crash without warning or worse. Data corruption or a system crash are quite unlikely but can't be ruled out.
{: .danger}
