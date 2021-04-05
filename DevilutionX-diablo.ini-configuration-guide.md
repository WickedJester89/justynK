# Welcome to DevilutionX diablo.ini configuration guide!  

The config folder path may differ depending on OS version and security settings, but will normally be as follows:  
- macOS `~/Library/Application Support/diasurgical/devilution`
- Linux `~/.local/share/diasurgical/devilution/`
- Windows `%AppData%\Roaming\diasurgical\devilution`

You can specify the location bypassing the switch --config-dir  

By changing these values, you can configure the game to your liking.
The options are divided into sections, where each adjustment comes with an individual description.
Setting a value outside the allowed parameters will cause the game to ignore the setting and use the built-in defaults.
The values below are the defaults as the game generates the file.  

[[Diablo]](#Diablo)  
[[Hellfire]](#Hellfire)  
[[Audio]](#Audio)  
[[Graphics]](#Graphics)  
[[Game]](#Game)  
[[Network]](#Network)  


# [Diablo]

### `Intro=1`  
0=disabled, 1=enabled;  
Enable/disable Intro cinematic.


# [Hellfire]

### `Intro=1`  
0=disabled, 1=enabled;  
Enable/disable Intro cinematic.  


# [Audio]

### `Sound Volume=0`  
0=Max Volume, -1600=No Sound;  
Adjust sound volume.  

### `Music Volume=0`  
0=Max Volume, -1600=No Music;  
Adjust music volume.  

### `Walking Sound=1`  
0=disabled, 1=enabled;  
Enable walking sound.  

### `Auto Equip Sound=0`  
0=disabled, 1=enabled;  
Enable Auto Equip sound.


# [Graphics]

### `Width=640`  
### `Height=480`  
These settings affect game area minimal resolution.  
The original game ran at 640x480, which corresponds to width=640 and height=480.  
You can now easily change to your desired resolution by changing values. For example for 1920x1080 you would enter width=1920 and height=1080.  

### `Fullscreen=1`  
0=Windowed, 1=Fullscreen;  
This sets the game to run in Windowed or Fullscreen  

### `Upscale=1`  
0=disabled, 1=enabled;  
Enable image upscaling to your current resolution, and allowing for window resizing.  

### `Fit to Screen=1`  
0=disabled, 1=enabled;  
Automatically adjust the game window to your current desktop screen aspect ratio and resolution.  

### `Scaling Quality=2`  
0=nearest neighbor, 1=bilinear, 2=anisotropic;  
Enables optional filters to the output image when upscaling.

### `Integer Scaling=0`  
0=disabled, 1=enabled;  
Scales the image using whole number pixel ratio. 

### `Vertical Sync=1`  
0=disabled, 1=enabled;  
Forces waiting for Vertical Sync. Prevents tearing effect when drawing a frame.  

### `Blended Transparency=1`  
0=disabled, 1=enabled;  
Enables uniform transparency mode.  
This setting affects the transparency on walls, game text menus, and boxes.  
If disabled will default to old checkerboard transparency.  

### `Gamma Correction=100`  
Min=100, Max=30;  
Adjust game brightness setting the lower the number the brighter the screen.  

### `Color Cycling=1`  
0=disabled, 1=enabled;  
Enable color cycling effect used for water, lava, and acid animation.  

### `FPS Limiter=1`  
0=disabled, 1=enabled;  
When enabled FPS is limited to avoid high CPU load. When disabled the FPS will go as high as your CPU will allow.  


# [Game]

### `Speed=20`  
1=Min, 20=Default, 1000=Max;  
Adjust the rate at which game events take place. Besides the max, this will also be caped by your fps.
Beware! It affects not only the player but also the monsters.


### `Fast Walk=0`  
0=disabled, 1=enabled;  
Enable jog/fast walking in town for Diablo and Hellfire. This option was introduced in the expansion.  

### `Grab Input=0`  
0=disabled, 1=enabled;  
When enabled mouse is locked to the game window.  

### `Theo Quest=0`  
0=disabled, 1=enabled;  
Enable Little Girl quest. [Hellfire specific]  

### `Cow Quest=0`  
0=disabled, 1=enabled;  
Enable Jersey's Jersey quest. [Hellfire specific]  
Lester the farmer is replaced by the Complete Nut:  

### `Friendly Fire=1`  
0=disabled, 1=enabled;  
Allow arrow/spell damage between players in multiplayer even when friendly mode is on.

### `Test Bard=0`  
0=disabled, 1=enabled;  
Force the Bard character type to appear in hero selection menu.  

### `Test Barbarian=0`  
0=disabled, 1=enabled;   
Force the Barbarian character type to appear in hero selection menu.

### `Experience Bar=0`  
0=disabled, 1=enabled;  
Adds QoL feature Experience Bar.  
Experience Bar is added to the UI at the bottom of the screen.  

### `Enemy Health Bar=0`  
0=disabled, 1=enabled;  
Adds QoL feature Enemy Health Bar.
Enemy Health Bar is displayed at the top of the screen.  

### `Auto Gold Pickup=0`  
0=disabled, 1=enabled;  
Adds QoL feature Auto Gold Pickup.  
Gold is automatically collected when in close proximity to the player.  

### `Adria Refills Mana=0`  
0=disabled, 1=enabled;  
Adds QoL feature Adria Refills Mana.  
Adria will refill your mana when you visit her shop.  

### `Auto Equip Weapons=1`  
0=disabled, 1=enabled;  
Allows Auto Equip Weapons.  
Weapons will be automatically equipped on pickup or purchase if enabled.  
### `Auto Equip Armor=0`  
0=disabled, 1=enabled;  
Adds QoL feature Auto Equip Armor.  
Armor will be automatically equipped on pickup or purchase if enabled.  
### `Auto Equip Helms=0`  
0=disabled, 1=enabled;  
Adds QoL feature Auto Equip Helms.  
Helms will be automatically equipped on pickup or purchase if enabled.  
### `Auto Equip Shields=0`  
0=disabled, 1=enabled;  
Adds QoL feature Auto Equip Shields.  
Shields will be automatically equipped on pickup or purchase if enabled.  
### `Auto Equip Jewelry=0`  
0=disabled, 1=enabled;  
Adds QoL feature Auto Equip Jewelry.  
Jewelry will be automatically equipped on pickup or purchase if enabled.  

### `Randomize Quests=1`  
0=disabled, 1=enabled;  
Adds QoL feature to Disable the Randomized Quests in Single Player.  
Disables randomly selecting available quests each game, and lets all quests be present in one game.  
You need to start a new game for the setting to take effect.  

### `Show Monster Type=0`
0=disabled, 1=enabled;
Adds QoL feature that Shows Monster Type in UI.
When enabled if hovering over a monster that will display the type of monster in the description box in the UI.

# [Network]  
### `Bind Address=0.0.0.0`  
Limit what network card to make the game available on when hosting a game.

### `Port=6112`
1-65535;
Set the Port of a multiplayer game to any port from 1-65535.