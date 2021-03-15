## Download GoG's Diablo offline installer

## Install binary if available  

Get the latest Windows release from [Innoextract Github](https://github.com/dscharrer/innoextract/releases/latest)  
Ubuntu 20.04 and up you can install with `sudo apt install innoextract`  

## Install required dependencies for innoextract compilation

### innoextract requirements

From the innoextract [official install instructions](http://constexpr.org/innoextract/install) the stated dependencies are (taken verbatim and then edited):

1. a C++ compiler
2. CMake >= 2.8 or newer
3. Boost >= 1.37 (including development headers)
4. liblzma (from xz-utils, including development headers)
5. iconv (optional, via glibc, uClibc, or a separate libiconv)

### Ubuntu

These dependencies can be installed on an Ubuntu system with the following command (as detailed on the innoextract [official install instructions](http://constexpr.org/innoextract/install) page):

```
sudo apt install build-essential cmake libboost-all-dev liblzma-dev
```

### Other Operating Systems

Please consult your operating system's documentation and related texts for information on how to install the required dependencies.

## Install the latest git snapshot of innoextract

On Linux systems, and other similar systems, issue the following commands in your terminal:

```
git clone https://github.com/dscharrer/innoextract.git
cd innoextract/cmake/
cmake ..
make
sudo make install
```

Please note that this requires that git be installed on your system.

## Check innoextract version

The innoextract version must be >= 1.8 for it to be able to extract the MPQ from the GOG Diablo installer.

`innoextract --version`

Should return something similar to the following:

```
innoextract 1.8-dev + 08b1ee8
Extracts installers created by Inno Setup 1.2.10 to 6.0.2
```

## Get information about the GOG Diablo installer

In a terminal, run the following command: `innoextract --info 'setup_diablo_1.09_hellfire_v2_(30038).exe'` (adjust file name as appropriate)

This should return:

```
Inspecting "Diablo + Hellfire" - setup data version 5.6.2 (unicode)

Languages:
 - en-US

GOG.com game ID is 1412601690

Setup is not passworded!

```

## Extract DIABDAT.MPQ and the four Hellfire .MPQs from the installer

Linux: `innoextract -I DIABDAT.MPQ -I hellfire.mpq -I hfmonk.mpq -I hfmusic.mpq -I hfvoice.mpq 'setup_diablo_1.09_hellfire_v2_(30038).exe' && mv hellfire/h*.mpq ./ && rmdir hellfire`  

Windows: `innoextract -I DIABDAT.MPQ -I hellfire.mpq -I hfmonk.mpq -I hfmusic.mpq -I hfvoice.mpq setup_diablo_1.09_hellfire_v2_(30038).exe && move hellfire\h*.mpq .\ && rmdir hellfire`  

```  
Extracting "Diablo + Hellfire" - setup data version 5.6.2 (unicode)  
 - "DIABDAT.MPQ" [en-US]  
 - "hellfire/hellfire.mpq" [en-US]  
 - "hellfire/hfvoice.mpq" [en-US]  
 - "hellfire/hfmusic.mpq" [en-US]  
 - "hellfire/hfmonk.mpq" [en-US]  
Done.  
```  

## Copy the extracted MPQs to the required location  

Linux: `cp /some/path/*.mpq /some/new/path/*.mpq`  
Windows: `copy c:\some\path\*.mpq c:\some\new\path\*.mpq`  