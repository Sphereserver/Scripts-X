## --This script pack is in developement---

This script pack is designed to work with [![sphere X version](https://github.com/Sphereserver/Source-X)](https://github.com/Sphereserver/Source-X)

To be able use this pack correctly here the events you must add in ini
// Events related to all NPCs
EventsPet=e_npc_generic_event

// Events related to all players
EventsPlayer=e_player_generic_event,e_player_crafting_event

## ToDo
* Test map1 locations (is every teleport and area correct?)
* Add missing Stygian Abyss monsters, all High sea and TOL monsters and separate them by Era
* Update sphere_backwards_compatibility. Rename spk_horse, human, master to a more specific name (and change it to a job_*)
* Move the char height value from the DEFs height_0x or height_ to the CharDef! It's way faster to access that property from the chardef, and Sphere checks it VERY often!
* Rework template by era to be in concordance of ini settings: EraLimitGear / EraLimitLoot / EraLimitProps
