title:      HaloScript Data Types
desc:       Description of the different data types used in HaloScript
template:   document
nav:        HaloScript>Data Types
percent:    60
date:       2019/04/17
authors:    Num0005

HaloScript like most programming languages includes a number of data types, data types are just a way for the code to tell what sort of data it is working with (e.g. whatever it a sound tag or a string).

These can be broken into 3 main groups: internal, basic and complex.

### Internal ###

There are 4 types that are mostly used internally by the system: `unparsed`, `special form`, `function name` and `passthrough`.
Out of these the only one of note for us is `passthrough` as it can be "cast" or converted to any other type. See [Type Casting] for more.

## Basic ##

These are the basic types you would expect in a scripting language and are used by a lot of different functions.

| Name          | Description   |
| ------------- | ------------- |
| void          | Special type used to mean nothing, only as a function return type. |
| boolean       | True or false |
| real          | A float point number (1500.2, -1.53, 3.14159, etc) |
| short         | A whole number between -32767 and 32767 |
| long          | A whole number between -2147483647 and 2147483647 |
| string        | Text ("hello", "test", "120") |
| string_id     | Another way to reference a string-like value, sometimes used for localization |
| script        | Name of another script (cinematic_fade_from_black, welcome, etc) |

## Complex ##

Most HaloScript types belong in this category, these are mostly types added for use in a specific function. It can be further broken into multiple subsets: tags, enums, objects, object names and misc.

### Tags ###

These reference a specific tag, the compiler gets the tag datum and adds the tag to the References block in the scenario. 

The HaloScript compiler should check the tag type is correct,  but this check appears to be disabled by specifying the full path with extension
(`sound\ui\shield_hit.sound`, instead of `sound\ui\shield_hit`)
{: .info}

The following types are tags/tag refs:

* `sound`
* `effect`
* `damage`
* `looping_sound` 
* `animation_graph` 
* `damage_effect`
* `object_defintion`
* `bitmap`
* `shader`
* `render model`
* `structure definition`
* `lightmap definition`
* `style`

Style is only a tag ref in h2codez, it's non-functional in the release HEK and wasn't quite a tag ref in the Bungie HEK.
{: .info}

### Enums ###

Enums short for enumerated are used for named values.

| Name            | Description          | Value List |
| --------------- | -------------        | ---------- |
| game_difficulty | How hard the game is | Easy, Normal, Heroic, Legendary |
| team            | What team an AI or player is on, used in campaign | default, player, human, covenant, flood, sentinel, heretic, prophet, unused8, unused9, ... unused15 |
| actor_type      | unknown (code removed)|   N/A      |
| hud_corner      | Related to old HUD    |   N/A      |
| model_state     | TODO                  |   TODO     |
| network_event   | unknown (code removed)|   N/A      |

### Objects / Object Names ###

Objects and Object names with one minor different, objects can be set to `NONE` meaning no object and object names can't. So you can use `sound_impulse_start` without an object but not `object_create`

Objects have a complex set of rules relating to casting, once again see [Type Casting] for more.

The full list of object/object name types is:

* object
* unit
* vehicle
* weapon
* device
* scenery
