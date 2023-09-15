# Crafting System
Crafting system now is more dynamic. We use the craftion definitions to create the items and the properties based on the material.

in each crafting definition have a base resourceid, this is the base resource for the crafting.
```
blacksmithing_resourceid        "i_ingot_iron" //default material, is the base resourse that blacksmithing crafting use
```

## Example
This is a example of how to create a custom new ore, called Eclipse. This ore can be used to craft armor and weapons. The ore is a colored ore, so the items will be colored with the color of the ore.

add in def_blacksmithing, in the sphere_crafting_blacksmithing_colored  
```
blacksmithing_material_9_name		    "Eclipse"                               // this is the name to display in the gump
blacksmithing_material_9_skill		    "Blacksmithing 99.0"                    // skill require to access to this material
blacksmithing_material_9_color		    "0145"                                  // color of the material (apply to the item if the colored is enabled)
blacksmithing_material_9_resourceid	    "i_ingot_eclipse"                       // resource id of the material to override the default
blacksmithing_material_9_aftercraft     "f_blacksmithing_aftercraft_eclipse"    //function to call after craft the item 
```

create the custom ore and  ingot
```
[ITEMDEF i_ore_eclipse]
ID=i_ore_iron
NAME=eclipse ore
SKILLMAKE=mining 95.0
TDATA1=i_ingot_eclipse
VALUE=15

CATEGORY=Resources
SUBSECTION=Ores
DESCRIPTION=Eclipse ore

ON=@Create
    COLOR=0145

[ITEMDEF i_ingot_eclipse]
NAME=eclipse ingot
ID=i_ingot_iron
RESOURCES=i_ore_eclipse
SKILLMAKE=mining 95.0
TDATA1=90.0
TDATA2=120.0

CATEGORY=Resources
SUBSECTION=Ingots
DESCRIPTION=Eclipse ingot

ON=@Create
   COLOR=0145
```

create function to apply attributes to items
```
[FUNCTION f_resource_ore_aftercraft_eclipse]
IF (<ISARMOR>)
    MODAR = 10
ELIF (<ISWEAPON>)
    HITPOINTS += 10
ENDIF
```


## TODO
- Tailoring: add repair function (is enabled on AOS)
- Check EXPANSION in the aftercraft function to see what properties are enabled
- After check EXPANSION. Add the resistances to each resource
