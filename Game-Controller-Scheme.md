DevilutionX supports most gamepad controls.

Default controller mappings (A/B/X/Y as in Nintendo layout, so the rightmost button is attack; A ○, B ×, X △, Y □):

- Left analog or D-Pad: move hero
- A: attack nearby enemies, talk to townspeople and merchants, pickup/place items in the inventory, OK while in main menu
- B: select spell, back while in menus
- X: pickup items, open nearby chests and doors, use item in the inventory
- Y: cast spell, delete character while in main menu
- L1: use health item from belt
- R1: use mana potion from belt
- L2: character sheet (alt: Start + L1 or ←)
- R2: inventory (alt: Start + L2 or →)
- Left analog click: toggle automap (alt: Start + ↓)
- Start + Select: game menu (alt: Start + ↑)
- Select + A/B/X/Y: Spell hotkeys
- Right analog: move automap or simulate mouse
- Right analog click: left mouse click (alt: Select + L1)
- Select + Right analog click: right mouse click (alt: Select + R1)
- Select + L2: quest log (alt: Start + Y)
- Select + R2: spell book (alt: Start + B)

For now, they can be re-mapped by changing `SourceX/controls` or by setting the `SDL_GAMECONTROLLERCONFIG` environment
variable (see
[SDL_GameControllerDB](https://github.com/gabomdq/SDL_GameControllerDB)).
