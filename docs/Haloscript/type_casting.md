title:      HaloScript Type Casting
desc:       Description of the different data types used in HaloScript
template:   document
nav:        HaloScript>Type Casting
percent:    100
date:       2020/02/19
authors:    Num0005

HaloScript supports converting data from one type to another, this is called type casting or just casting. Type casting in HaloScript is done automatically when needed but it's good to keep it in mind as not 
all types can be converted. Passthrough can be converted to any type and void can be converted to from any type. They are however not the inverse of each other as void destroys the data during conversion.

| Target Type     | Source type(s)            | 
| --------------- | ----------------          |
| boolean         | real, long, short, string |
| real            | any enum, short, long     |
| long            | short, real               |
| short           | long, real                |
| object_list     | any object or object_name |
| void            | any type                  |
| any type        | passthrough               |
| object          | no other object type      |
| unit            | object                    |
| vehicle         | object, unit              |
| weapon          | object                    |
| device          | object                    |
| scenery         | object                    |
