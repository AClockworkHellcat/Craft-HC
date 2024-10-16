# Craft-HC

It's Craft, but with some vital improvements by yours truly:
## Differences
- added set.length() function to sets.lua; the devs never document their libs, so I could only assume its absence meant trying to use tables.length() would find a way to break it, even though Lua "objects" are just tables.
- altered recipe list for consistency, prioritizing the most convenient versions of recipes over others, eg. leather using tea leaves before willow logs, ingots prioritizing ore over beastcoins and nuggets, etc.
- properly named batch-processing recipes to differentiate them from the standard recipes
- made the find function useful; you can now search for recipes by name or by ingredient
- addon now starts paused, with support enabled and Escape as the jiggle key by default.
- processing Rocks, Geodes, Sparkling Stones, Scholar Stones, Avatarites, kits, and broken fishing rods will now use the input item's name
- recipes use proper names rather than FFXI's horribly inconsistent abbreviations
- those of you working on a shield can make Sets without the HQ crystals interfering

## Instructions
### Commands:
(Copied straight from the script.)
1.  help - Displays the command list.
2.  repeat - Repeats synthesis (default 1) using the
    /lastsynth command.
* repeat - Repeats 1 synthesis
* repeat 13 - Repeats 13 synthesis
3.  make - Issue a synthesis command using a recipe name
* make "Sheep Leather" - Makes 1 Sheep Leather
* make "Sheep Leather" 5 - Makes 5 Sheep Leather
4.  put - Moves all copies of an item into available bags.
* put "Dragon Mask" - Moves all Dragon Masks in inventory
  to any available bags.
* put "Dragon Mask" satchel - Moves all Dragon Masks in
  inventory to Mog Satchel.
* put "Dragon Mask" safe2 - Moves all Dragon Masks to Mog
  Safe 2 (if available).
5.  delay - Sets the delay between crafting attempts
    (default 24, minimum 17)
* delay 30 - Sets the delay between crafting to 30
  seconds. (24~26 usually works.)
6.  food - Sets a food item that will automatically
    be consumed while crafting.
* food - Sets the auto food to None.
* food "Kitron Macaron" - Sets the auto food
  to Kitron Macaron.
7.  pause - Pauses the crafting process. (This version starts paused.)
8.  resume - Resumes the crafting process.
* start - Also resumes the crafting process.
9. clear - Clears all items in the queue.
10. jiggle - Set a key that will be pressed between every
    queue item (default disabled.)
* jiggle - Disables the jiggle feature.
* jiggle escape - Sets the jiggle key to escape.
11. support - Toggles auto support/ionis (default off)
* Must be near an NPC that offers Ionis or advanced
  imagery support to work.
* Determines whether items will be sold instantly or slowly.
12. status - Display some information about the
    addon's current state.
13. find - Search for a recipe fromt the recipes list using
    a string.
* find "Rock" - Finds and displays the names of recipes
  containing the string "Rock" somewhere
* find "Rock" details - Finds and displays all recipes
  containing the string "Rock" somewhere (including
  ingredients and crystal)
* find "Rock Salt" recipe - Finds and displays all
  recipes, in full, to craft items whose names contain the
  string "Rock Salt"
* find "Rock Salt" ingredient - Finds and displays all
  recipes, in full, whose ingredients contain the string
  "Rock Salt"
14. display - Toggles whether outgoing crafting
    packets are displayed in the chat log.
15. hqcrystal - Toggle whether to use HQ Crystal

### Notes:
  Make commands will automatically pull items from
  any available bags if they are not present in your
  inventory.  This includes all recipe ingredients
  and the crystal.  If a crystal cannot be found,
  it will search for a cluster from your inventory
  and available bags and use the cluster.  These
  features are not supported with the repeat command.

  The available recipes are stored in recipes.lua.
  To add new recipes, enable the display (//craft
  display) and manually craft an item.  The packet will
  be printed to your chat log.  Create an entry similar
  to the recipes that are already provided.  Only add
  the actual ingredients and crystal.  Then save
  recipes.lua and reload the addon.

  Ingredients and food are case sensitive and use
  the short english name.  These are the ones
  displayed on FFXIAH. Recipes, however, use sensible
  names because FFXI's abbreviations are inconsistent.

## Conceivable questions:

### Q: Why use the input item's name instead?
A: For one thing, who's out here processing rocks/geodes/etc. hoping to get the lowest-tier result? For another, who has every possible result from a given rock memorized? And for a third, why should fixing a broken fishing rod be the default recipe for that rod, thus relegating actually crafting a new one to #2, when it can just be a different recipe?

### Q: Why re-number recipes with multiple versions?
A: Consistency and sensibility, mostly. There's no reason the recipes that use Beastcoins, which have to be farmed from mobs, should be #1 for ingots, especially when most ingots don't have Beastcoin recipes, and just use ores as their default. Nuggets are less efficient than ores, but they're almost as readily available; and since not all ingot recipes use them, but there are more ingots that use nuggets than Beastcoins, they get to be #2. Likewise, every type of leather can use Tea Leaves as an ingredient, but not every type can use Willow Logs, and leather batches can't use Willow Logs at all, so it makes no sense whatsoever to put the ones using Willow Logs as the #1 recipe under any circumstances. Doing it my way, you won't have to search for the right version of every recipe to find the one that matches the ingredients you want to use. You will still have to search for some of the more nonsensical ones, though; the few with 4+ variants don't have any rhyme or reason to them.

### Q: You're expecting too much from the original creator.
A: I expect creators not to make their end users do their jobs for them. The original creator scraped BGWiki for recipes and called it a day without even verifying them, let alone sorting them; and because he wanted to avoid a few moments of minor inconvenience during development by not even trying to put the recipes in a sensible order, we got to endure those moments of inconvenience every single time we wanted to do a lot of crafting. And since his search function was absolute pants, it was made even more inconvenient by having to sift through every result that included any mention of whatever item we were trying to make just to find the right recipe. If you claim something you made will make a task more convenient, but it instead adds enough additional inconvenience to offset its utility, you messed up.

### Q: Why do you do these passive-aggressive unauthorized forks instead of submitting fixes?
A: One, because if anybody I fork from was actually maintaining anything, they'd already have fixed the things I needed to fix. Two, because some of the addons I have to fix are officially-"supported" Windower addons, which means they'll just get clobbered arbitrarily by the launcher. Three, because I don't feel like learning how the system works; just pushing updates to my own repos is annoying enough. And last, because I really don't feel like interacting with people whose job I had to do for them, even if they haven't drifted off into the void by now.

## Known Issues
- None so far
