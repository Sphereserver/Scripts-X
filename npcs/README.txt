TODO:
-Most NPCs here seems to do not have sound and resistances
-resphysical must be added as resistance, it works different than armor
-armor values doesn't even approach to resphysical
-Elemental damages are missing
-Lots of stats/skills does not match uoguide/stratics
-Fixed values on stat/skills must be fixed, not ranged
-There are NPCs with skills they shouldn't even have.
-TAG.BARDING.DIFF missing in most npcs
-KARMA/FAME values does not match
-Mount icons placed here, should be moved to i_char_icons.scp? some of them are duplicated -> remove
-missing FACTIONS 


coding guidelines:

-reserved keywords UPPERCASE, values after it in lowercase (use capitals for names).
-Tabs must be changed to 4 white spaces.
-Any property that shares the same value over all objects of it's same ID must be placed on it's block instead of it's triggers (excepting for random values):
    [WHATEVER ] blocks ([CHARDEF in this case]) can only have fixed values, random ones must go inside triggers, eg:
    [CHARDEF xx]
    DAMFIRE=15 // correct
    DAMFIRE={15 25} // incorrect, this one must be placed in ON=@Create
    
    ON=@Create
    DAMFIRE=15 // legit, but not recommended, fixed values for all characters are better placed above, so this prop is not required to be saved
    DAMFIRE={15 25} //correct

Chardef example:
[CHARDEF xxx]
//base defs
DEFNAME=c_xx
NAME=Some Name
ICON=
SOUND=

//Fixed values' properties and tags. Fixed only, ranges are not allowed here.
DAM=15,20
DAMFIRE=20
FACTION=faction_demon   // defnames in lowercase
BLOODCOLOR=1
TAG.BARDING.DIFF=95.0

//Aversions, resources, etc
DESIRES=r_dungeon_doom,t_coin,t_gold,t_gem,t_wand,t_potion,t_scroll,t_reagent
AVERSIONS=t_trap,r_civilization
RESOURCES=1 i_reag_blackmoor

//TEVENTS
TEVENTS=e_carnivores

//TSPEECH
TSPEECH=spk_human

//ResDisp*
RESDISPDNID=c_elem_air
RESLEVEL=2
RESDISPDNHUE=55

//Expansion settings
ERALIMITLOOT=1
ERALIMITGEAR=1
ERALIMITPROPS=1

//GM Tools categories
CATEGORY=Monsters
SUBSECTION=Elementals
DESCRIPTION=Elemental, Example

ON=@Create
    //Even with fixed size, brain, color, fame/karma skills and stats must be added in @Create
    //Brain first
    NPC=brain_monster
    
    //Fame/karma
    FAME=10000
    KARMA=-10000
    
    //Color, if required
    COLOR=colors_slime
    
    //Stats
    STR={100 150}
    DEX={120 130}
    INT={15 20}
    MAXHITS={120 160}
    
    //From here, excepting skills, can be placed here for random values or in the [CHARDEF ] block for fixed values.
    //Resistances   //Resphysical is also required, armor can be added for backwards but having armor doesn't mean that resphysical isn't required and viceversa.
    RESPHYSICAL={55 65}
    RESFIRE={30 35}
    RESCOLD={40 45}
    RESPOISON=0 // Any property with a value of 0 should not be added, just remove the whole line
    
    //Damages (if not fixed, fixed values are placed above)
    //DAMPHYSICAL can be added but if it's not present it will be defaulted to RESPHYSICAL = 100 - (RESFIRE+RESCOLD+RESPOISON+RESENERGY)
    DAMCOLD={30 35}
    
    //Skills
    MAGERY={350 500}
    MEDITATION={700}    //RANGES should NEVER be added for a single value, this should be MEDITATION=700
    
    //Other not-fixed properties
    HitLeechLife={35 40}

ON=@CreateLoot
    ITEM=xxx // loot behaviour