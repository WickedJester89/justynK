# Setting up devilutionX using a Windows machine networked to your Pie

## Ports Directory

1. **Create** a folder called `diablo`.

2. **Copy** your `diabdat.mpq` into it **(make sure to rename it lowercase)**.

3. **Download** the latest [release](https://github.com/diasurgical/devilutionX/releases) of `linux-armhf.7z`.

4. **Extract** `devilutionx` and `devilutionx.mpq` into the `diablo folder`.

5. **Create** another folder inside the `diablo folder` called `gamedata` (we'll use this later).

6. **Open** Windows Explorer and navigate to the ports directory on your pie `\\retropie\roms\ports\`.

7. **Copy** the `diablo` folder to this directory.

![Capture](https://user-images.githubusercontent.com/17083706/110678286-1dd43c00-81a4-11eb-9944-d120ba02da9b.PNG)

8. **Create** a file called `Diablo.sh`

9. **Add** the following to it:

`#!/bin/bash`

`"/opt/retropie/supplementary/runcommand/runcommand.sh" 0 _PORT_ "diablo" ""`

10. **Copy** `Diablo.sh` to `\\retropie\roms\ports\`.

![image](https://user-images.githubusercontent.com/17083706/110678703-9cc97480-81a4-11eb-9cab-56f6a607ecf0.png)

***

## Configs Directory

1. **Create** a second folder called `diablo` (or delete everything inside the first one on the Windows machine).

2. **Create** a file inside it called `emulators.cfg`

3. **Add** the following to it:

`diablo = "/home/pi/RetroPie/roms/ports/diablo/devilutionx --save-dir /home/pi/RetroPie/roms/ports/diablo/gamedata"`

`default = "diablo"`

4. **Open** Windows Explorer and navigate to the ports config directory on your pie `\\retropie\configs\ports`.

5. **Copy** the `diablo` folder to this directory.

![image](https://user-images.githubusercontent.com/17083706/110678534-6855b880-81a4-11eb-8ca8-1b0b2947ab1b.png)

***

## Execution Rights and Dependencies

1. **Open** the Retropie `configuration menu` on your pie.

2. **Open** the `FileManager`.

3. **Navigate** to the Diablo folder in the ports directory `/home/pi/RetroPie/roms/ports/diablo/`.

4. **Type** `chmod u+x devilutionx` to grant execution rights. 

5. **Hit** `Ctrl+o` on your keyboard to bring up the full terminal.

6. **Type** `apt install libsdl2-2.0-0` and install.

8. **Type** `exit` to exit terminal then `F10` to exit the file mananger.

***

## Diablo.ini
1. **Select** Diablo in the Ports menu to run it for the first time (generates default `.ini`).

2. **Open** Windows Explorer and navigate to the `gamedata` folder on your pie `\\retropie\roms\ports\diablo\gamedata`.

3. **Open** `diablo.ini` to make any changes.

(Your character saves will be stored here as well)
***

## Troubleshooting

If you do not have a ports menu:

1. **Open** the Retropie `configuration menu` on your pie.

2.  **Select** `Retropie Setup`

3. **Select** `Manage Packages -> Manage Optional Packages -> Kodi -> Install`

4. **Restart** the emulationstation.

If your pi has a black boarder around the screen:

1. **Open** the Retropie `configuration menu` on your pie.

2. **Select** `Raspi-Config`

3. **Select** `Dispaly Options -> UnderScan -> No -> Restart`
