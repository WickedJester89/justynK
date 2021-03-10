# Setting up devilutionX using a Windows machine networked to your pi

1. **Create** a folder called `Diablo`.

2. **Copy** your `diabdat.mpq` into it **(make sure to rename it lowercase)**.

3. **Download** the latest [release](https://github.com/diasurgical/devilutionX/releases) of `linux-armhf.7z`.

4. **Extract** `devilutionx` and `CharisSILB.ttf` into the `Diablo folder`.

5. **Create** another folder inside the `Diablo folder` called `gamedata` (we'll use this later).

6. **Open** windows explorer and navigate to the ports directory on your pi `\\retropie\roms\ports\`.

7. **Copy** the `Diablo` folder to this directory.

8. **Create** a file called `Diablo.sh`

9. **Add** the following to it:

`#!/bin/bash`

`"/opt/retropie/supplementary/runcommand/runcommand.sh" 0 _PORT_ "diablo" ""`

10. **Copy** `Diablo.sh` to `\\retropie\roms\ports\`.


***


1. **Create** a second folder called `Diablo` (or delete everything inside the first one on the Windows machine).

2. **Create** a file inside it called `emulators.cfg`

3. **Add** the following to it:

`diablo = "/home/pi/RetroPie/roms/ports/diablo/devilutionx --save-dir /home/pi/RetroPie/roms/ports/diablo/gamedata"`

`default = "diablo"`

4. **Open** Windows Explorer and navigate to the ports config directory on your pi `\\retropie\configs\ports`.

5. **Copy** the `Diablo` folder to this directory.


***

1. **Open** the Retropie `configuration menu` on your pi.

2. **Open** the `FileManager`.

3. **Navigate** to the Diablo folder in the ports directory `/home/pi/RetroPie/roms/ports/diablo/`.

4. **Type** `chmod u+x devilutionx` to grant execution rights. 


***

1. **Select** Diablo in the Ports menu to run it.

2. **Open** Windows Explorer and navigate to the `gamedata` folder on your pi `\\retropie\roms\ports\diablo\gamedata`.

3. **Open** `diablo.ini` to make any changes.


***

## Troubleshooting:

If the launch menu comes up but the game does not run, make sure you have the SDL dependencies installed:

`apt install libsdl2`

`apt install libsdl2-mixer`

`apt install libsdl2-ttf`

If sound effects are sometimes distorted, check if you have a -dev install of mixer and uninstall it:

`apt remove libsdl2-mixer-dev`

If your pi has a black boarder around the screen:

1. **Open** the Retropie `configuration menu` on your pi.

2. **Select** `Raspi-Config`

3. **Select** `Dispaly Options -> UnderScan -> No -> Restart`
