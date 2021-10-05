To help you get your debugging job done, there is a rich set of debug commands (some call them cheats) which could be used when running a version which has been compiled in debug mode. So these cheats are not available in releases at the moment.
You can enter them anytime in-game by pushing Enter and typing.

At the moment there are:

| Command       | Description                                                           |
| ------------- | --------------------------------------------------------------------- |
| help          | Prints help overview or help for a specific command.                  |
| give gold     | Fills the inventory with gold.                                        |
| give xp       | Levels the player up (min 1 level or {levels}).                       |
| setspells     | Set spell level to {level} for all spells.                            |
| take gold     | Removes all gold from inventory.                                      |
| give quest    | Enable a given quest.                                                 |
| give map      | Reveal the map.                                                       |
| changelevel   | Moves to specifided {level} (use 0 for town).                         |
| map           | Load a quest level {level}.                                           |
| visit         | Visit a towner.                                                       |
| restart       | Resets specified {level}.                                             |
| god           | Toggles godmode.                                                      |
| r_drawvision  | Toggles vision debug rendering.                                       |
| r_fullbright  | Toggles whether light shading is in effect.                           |
| fill          | Refills health and mana.                                              |
| dropu         | Attempts to generate unique item {name}.                              |
| drop          | Attempts to generate item {name}.                                     |
| talkto        | Interacts with a NPC whose name contains {name}.                      |
| exit          | Exits the game.                                                       |
| arrow         | Changes arrow effect (normal, fire, lightning, explosion).            |
| grid          | Toggles showing grid.                                                 |
| seedinfo      | Show seed infos for current level.                                    |
| spawn         | Spawns monster {name}.                                                |
| tiledata      | Toggles showing tile data {name} (leave name empty to see a list).    |
| scrollview    | Toggles scroll view feature (with shift+mouse).                       |
| iteminfo      | Shows info of currently selected item.                                |
| questinfo     | Shows info of quests.                                                 |
| playerinfo    | Shows info of player.                                                 |

You can find the debug commands in Source/debug.cpp