# Extracting the DIABDAT.MPQ from the GoG installer

- Install [innoextract](https://constexpr.org/innoextract/); the program is open source and cross-platform, with releases for all major operating systems.
- Navigate to the directory containing your GoG Diablo installer .exe
- Run the command `innoextract <name_of_your_installer>.exe`. 

This will output the entire contents of the .exe in the same directory as the .exe file, including DIABDAT.MPQ.