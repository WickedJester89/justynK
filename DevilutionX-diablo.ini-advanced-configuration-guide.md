# Welcome to DevilutionX diablo.ini advanced configuration guide!

By changing these values, you can configure the game to your liking.
The options are divided in sections, where each adjustment comes with individual description.
Setting a a value outside the allowed parameters will cause the game to ignore the setting and use the built in defaults. 


## [Cinematics]

### Enable/disable Intro cinematic.
1=enabled, 0=disabled;

[Hellfire]

`Intro=0`

[Diablo]

`Intro=0`


## [Audio]

### Adjust sound volume.
0= sound disabled, Max value is 100;

`Sound Volume=0`

### Adjust music volume.
0= sound disabled, Max value is 100;

`Music Volume=0`

### Enable walking sound.
1=enabled, 0=disabled;

`Walking Sound=1`

### Enable Auto Equip sound.
1=enabled, 0=disabled;

`Auto Equip Sound=0`


## [Graphics]

### These settings affect display resolution of the game.
The original game ran at 640x480, which corresponds to width=640 and height=480.
You can now easily change to your desired resolution by entering the following values width=1920 and height=1080.

`Width=960`

`Height=540`

### This forces the game to run in Window or Fullscreen
Window=0, Fullscreen=1

`Fullscreen=1`

### Forces image to be upscaled to your current desktop resolution, maintaining the aspect ratio of the in game resolution.
enabled 1=enabled, 0=disabled;

`Upscale=1`

### Fits automatically game resolution to your current desktop screen settings.
1=enabled, 0=disabled;

`Fit to Screen=1`

### Enables filtering for better quality image.
1=bicubic, 2=bilinear, 0=nearest neighbor 

`Scaling Quality=0`

### Scales the image using whole number pixel ratio.
enabled 1=enabled, 0=disabled;

`Integer Scaling=1`

### Forces waiting for Vertical Sync. Prevents tearing effect when drawing a frame.
1=enabled, 0=disabled;

`Vertical Sync=1`

### Enables a better transparency mode.
New blended transparency affects the transparency on walls, game text menus and boxes.
If disabled will default to old checkerboard transparency.

1=enabled, 0=disabled;

`Blended Transparency=1`

### Adjust game brightness setting.
min.value=0, max.value=100;

`Gamma Correction=100`

### Enable color cycling animation used for water, lava, acid animation.
1=enabled, 0=disabled;

`Color Cycling=1`

### Limits framerate.???
1=enabled, 0=disabled;

`FPS Limiter=1`

## [Gameplay]

### Adjust the rate at which game events take place.
Beware! It affects not only the player but also the monsters.
Default value=20, Max value=100;

`Speed=20`

### Enable jog/fast walking in town introduced in Hellfire.
1=enabled, 0=disabled;

`Fast Walk=0`

### Grab input????
1=enabled, 0=disabled;???

`Grab Input=0`

### Enable Little Girl quest. [Hellfire specific]
1=enabled, 0=disabled;

`Theo Quest=0`

### Enable Jersey's Jersey quest.[Hellfire specific]
Lester the farmer is replaced by the Complete Nut:

1=enabled, 0=disabled;

`Cow Quest=0`

### Enables or disables damage between players in multiplayer game.
1=enabled, 0=disabled;

`Friendly Fire=1`

### Enables Bard character type in hero selection menu.
1=enabled, 0=disabled;

`Test Bard=1`

### Enables Barbarian character type in hero selection menu.
1=enabled, 0=disabled;

`Test Barbarian=1`

### Add Experience Bar to game HUD.
1=enabled, 0=disabled;

`Experience Bar=1`

### Adds Qol feature Enemy Health Bar on top of the screen.
1=enabled, 0=disabled;

`Enemy Health Bar=1`

### Adds Qol feature Auto Gold Pickup.
Gold is automatically collected when in close proximity to the player.

1=enabled, 0=disabled;

`Auto Gold Pickup=1`

### Adds Qol feature Adria Refills Mana.
Adria will refill your mana when you visit her shop.

1=enabled, 0=disabled;

`Adria Refills Mana=1`

### Adds Qol feature selective Auto Equip.
Items from the list below will be automatically equipped on pickup.

1=enabled, 0=disabled;

`Auto Equip Weapons=1`

`Auto Equip Armor=0`

`Auto Equip Helms=0`

`Auto Equip Shields=0`

`Auto Equip Jewelry=0`

### Enables all Quest in Single Player.
You need to start a new game for the setting to take effect.

1=enabled, 0=disabled;

`Enable All Quests for Single Player=0`

## [Network]

### Set a external IP address for multiplayer game.???

`Bind Address=0.0.0.0`
