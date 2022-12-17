# New Features

One major change with this update is that big key doors and certain trap doors are no longer guaranteed to be vanilla in Dungeon Door Shuffle modes even if you choose not to shuffle those types. A newer algorithm for putting dungeons together has been written and it will remove big key doors and trap doors when necessary to ensure progress can be made.

Please note that retro features are now independently customizable as referenced below. Selecting Retro mode or World State: Retro will change Bow Mode to Retro (Progressive). Take Anys to Random, and Small Keys to Universal.

## Flute Mode

Normal mode for flute means you need to activate it at the village statue after finding it like usual.
Activated flute mode mean you can use it immediately upon finding it. the flute SFX plays to let you know this is the case.

## Bow Mode

Four options here:

* Progressive. Standard progressive bows.
* Silvers separate. One bow in the pool and silvers are a separate item.
* Retro (progressive). Arrows cost rupees. You need to purchase the single arrow item at a shop and there are two progressive bows places.
* Retro + Silvers. Arrows cost rupees. You need to purchase the single arrow item or find the silvers, there is only one bow, and silvers are a separate item (but count for the quiver if found).

## Dungeon Shuffle Features

### Small Keys

There are three options now available:

* In Dungeon: The small key will be in their own dungeon
* Randomized: Small keys can be shuffled outside their own dungeon 
* Universal: Retro keys without the other options

### Dungeon Door Shuffle

New mode: Partitioned. Partly between basic and crossed, dungeons are shuffled in 3 pools:

* Light World dungeons, Hyrule Castle and Aga Tower are mixed together
* Palace of Darkness, Swamp Palace, Skull Woods, and Thieves Town are mixed together 
* The other dark world dungeons including Ganons Tower are mixed together

### Door Types to Shuffle

Four options here, and all of them only take effect if Dungeon Door Shuffle is not Vanilla:

* Small Key Doors, Bomb Doors, Dash Doors: This is what was normally shuffled previously
* Adds Big Keys Doors: Big key doors are now shuffled in addition to those above, and Big Key doors are enabled to be on in both vertical directions thanks to a graphic that ended up on the cutting room floor. This does change
* Adds Trap Doors: All trap doors that are permanently shut in vanilla are shuffled.
* Increases all Door Types: This is a chaos mode where each door type per dungeon is randomized between 1 less and 4 more.

Note: Boss Trap doors are removed currently and not added into the trap door pool as extra trap doors. This may not be a permanent change

### Decouple Doors

This is similar to insanity mode in ER where door entrances and exits are not paired anymore. Tends to remove more logic from dungeons as many rooms will not be required to traverse to explore. Hope you like transitions.

## Customizer

Please see [Customizer documentation](docs/Customizer.md) on how to create custom seeds.

## New Goals

### Triforce Hunt + Ganon
Collect the requisite triforce pieces, then defeat Ganon. (Aga2 not required). Use `ganonhunt` on CLI

### Completionist
All dungeons not enough for you? You have to obtain every item in the game too. This option turns on the collection rate counter and forces accessibility to be 100% locations. Finish by defeating Ganon.


## Standard Generation Change

Hyrule Castle in standard mode is generated a little differently now. The throne room is guaranteed to be in Hyrule Castle and the Sanctuary is guaranteed to be beyond that. Additionally, the Mirror Scroll will bring you back to Zelda's Cell or the Throne Room depending on what save point you last obtained, this is to make it consistent with where you end up if you die. If you are lucky enough to find the Mirror, it behaves differently and brings you the last entrance used - giving you more options for exploration in Hyrule Castle.

## ER Features

### New Experimental Algorithm

To accommodate future flexibility the ER algorithm was rewritten for easy of use. This allows future modes to be added more easily. This new algorithm is only used when the experimental flag is turned on.

### Lite/Lean ER (Experimental required)

Designed by Codemann, these are available now (only with experimental turned on - they otherwise fail)

#### Lite
- Dungeon and multi-entrance caves can only lead to dungeon and multi-entrance caves
- Dropdowns can only lead to dropdowns, with them staying coupled to their appropriate exits
- Cave entrances that normally lead to items can only lead to caves that have items (this includes Potion Shop and Big Bomb Shop)
- All remaining entrances remain vanilla
- Multi-entrance caves are connected same-world only
- LW is guaranteed to have HC/EP/DP/ToH/AT and DW: IP/MM/TR/GT
- Shop locations are included in the Item Cave pool if Shopsanity is enabled
- Houses with pots are included in the Item Cave pool if Pottery is enabled

#### Lean
- Same grouping/pooling mechanism as in Lite ER
- Both dungeons and connectors can be cross-world connections
- No dungeon guarantees like in Lite ER

### Back of Tavern Shuffle (Experimental required)

Thanks goes to Catobat which now allows the back of tavern to be shuffled anywhere and any valid cave can be at the back of tavern with this option checked. Available in experimental only for now as it requires the new algorithm to be shuffled properly.

#### Take Any Caves

These are now independent of retro mode and have three options: None, Random, and Fixed. None disables the caves. Random works as take-any caves did before. Fixed means that the take any caves replace specific fairy caves in the pool and will be at those entrances unless ER is turned on (then they can be shuffled wherever). The fixed entrances are:

* Desert Healer Fairy
* Swamp Healer Fairy (aka Light Hype Cave)
* Dark Death Mountain Healer Fairy
* Dark Lake Hylia Ledge Healer Fairy (aka Shopping Mall Bomb)
* Bonk Fairy (Dark)

# Bug Fixes and Notes

* 1.2.0.1-u
  * Added new ganonhunt and completionist goals 
  * Fixed the issue when defeating Agahnim and standing in the doorway can cause door state to linger.
  * Fix for Inverted Lean/Lite ER
  * Fix for vanilla Doors + Standard + ER
  * Added a limit per dungeon on small key doors to ensure reasonable generation
  * Fixed many small bugs

# Known Issues

* Decoupled doors can lead to situations where you aren't logically supposed to go back through a door without a big key or small key, but you can if you press the correct direction back through the door first. There are some transitions where you may get stuck without a bomb. These problems are planned to be fixed.
* Logic getting to Skull X room may be wrong if a trap door, big key door, or bombable wall is shuffled there. A bomb jump to get to those pot may be required if you don't have boots to bonk across.