title:      DAEConverter Commands
desc:       A rundown of the commands the DAEConverter has.
template:   document
nav:        DAEConverter>Commands
percent:    100
date:       2018/12/07
authors:    General_101

| Name                          | Description                                                                                                                                                                                                                                                                                                         |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -compile (path)               | This command is used to compile your DAE files into render_model tags. Point it to a directory containing a proper folder structure. |
| -decompile (path)             | An experimental command used to dump meshes from render_model files into loadable OBJ files. Not guaranteed to work with all types of render_model tags. Especially different revisions of the tag. Point the path at a render_model file including the file extension. |
| -replace-node (path) (path)   | A command to workaround some of the issues the "-compile" command has with generated proper node inverse values. Proper usage is done by typing out the command. The first path is the render_model tag you want the values copied to and the second path is the render_model tags you want the values copied from. |
| -replace-marker (path) (path) | A command to quickly copy a list of markers from one model to another. Proper usage is done by typing out the command. The first path is the render_model tag you want the markers copied to and the second path is the render_model tags you want the markers copied from. |

-replace-marker only copies the first marker in a marker group properly at the moment. Every marker after the first will just be a duplicate.
{: .warning}
