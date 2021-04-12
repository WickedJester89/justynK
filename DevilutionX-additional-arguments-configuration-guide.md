# Welcome DevilutionX guide on how to run the game with additional arguments!

This guide will list and explain the available additional arguments when running DevilutionX. This will permit additional configurability when running the game.

[[How to use arguments]](#HowToUse)
[[Help and version]](#Help)
[[Config path and files]](#ConfigDir)
[[Game options]](#Game)
[[Hellfire options]](#Hellfire)

# [HowToUse]
Windows:
To apply these settings when starting the game under windows you have few options.


CMD / BAT file

Create text file in you `devilutionX folder`
Open it and enter the name of the DevilutionX executable followed by argument and parameter. [example: `devilutionx --data-dir d:\games\diablo`]
Save the file and rename its extension to .cmd
Use it to start the game.
Optionally you can create a shortcut to that file .


Shortcut file

When in DevilutionX left click on the executable and select create shortcut
Left click on the shotcut and select properties.
Under shortcut tab, target field, after the path and executable add the desired arguments and paths.
Use the shortcut to start the game.





### The following paragraphs will explain the arguments and their effects:

# [Help]


Print this message and exit
### `-h, --help`
The game will run and show a text help screen that briefly explains the arguments and then will terminate.


Print the version and exit
### `--version`
The game will run and show a text help screen that gives the game version and then will terminate.


# [ConfigDir]


Specify the folder of diabdat.mpq
### `--data-dir`
The game will run searching for the data files (diabdat.mpq, hellfire.mpq, etc.) in the specified folder path. This argument is used for both Diablo and Hellfire. This means that if you wish to play Hellfire, its .mpq  files must be located in the same path as diabdat.mpq.


Specify the folder of save files
### `--save-dir `          
The game will run and use the specified path after the argument as a save folder. Might need to be run with administrator permissions to be able to save in the desired path.


Specify the location of diablo.ini
### `--config-dir`
The game will run looking in the specified folder for the diablo.ini configuration file. If the file doesn’t exist one will be created. Might need administrator permissions to write in the desired folder.


Specify the location of the .ttf font
### `--ttf-dir`
The game will run looking for its default font used for displaying system messages and credits in the specified path.


Specify the name of a custom .ttf font
### `--ttf-name`
The game will run with the specific font of your choosing to display system messages and credits. You need to specify path and filename.


# [Game]


Skip startup videos
### `-n`
The game will skip all intro videos


Display frames per second
### `-f`
The game will run with fps counter in upper-left corner.


Run in windowed mode
### `-x`
The game will run in windowed mode.


Force spawn mode even if diabdat.mpq is found
### `--spawn`
The game will be forced to run in Diablo:spawn mode even if diabda.mpq exist. This allow you to explore only the cathedral level with the warrior. It features all the limitations of the original diablo spawn.


# [Hellfire]


Force diablo mode even if hellfire.mpq is found
### `--diablo`

The game will run in Diablo mode even if Hellfire data files are present along diabdat.mpq in either current or specified data-dir.


Use alternate nest palette
### `--nestart`

The game will use an alternative palette for the Hellfire’s nest tileset. This option is similar to the command.txt from the original expansion.
