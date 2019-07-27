## Download GoG's Diablo offline installer

## Install required dependencies for innoextract compilation

### innoextract requirements

From the innoextract [official install instructions](http://constexpr.org/innoextract/install) the stated dependencies are (taken verbatim and then edited):

1. a C++ compiler
2. CMake >= 2.8 or newer
3. Boost >= 1.37 (including development headers)
4. liblzma (from xz-utils, including development headers)
5. iconv (optional, via glibc, uClibc, or a separate libiconv)

### Ubuntu

These dependencies can be installed on an Ubuntu system with the following command (as detailed on the innoextract [official install instructions](http://constexpr.org/innoextract/install) page:

```
sudo apt-get install build-essential cmake libboost-all-dev liblzma-dev
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

## Extract DIABDAT.MPQ from the installer

`innoextract --include DIABDAT.MPQ --lowercase 'setup_diablo_1.09_hellfire_v2_(30038).exe'`

Note that we need the file to have a lowercase file name, thus the `--lowercase` in the above command.

```
Inspecting "Diablo + Hellfire" - setup data version 5.6.2 (unicode)
 - "diabdat.mpq" [en-US]
Done.
```

## Copy the extracted diabdat.mpq to the required location

`cp /some/path/diabdat.mpq /some/new/path/diabdat.mpq`