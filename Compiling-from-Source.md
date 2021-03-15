# 32-bit building on 64-bit platforms
## Linux
### Installing dependencies on Debian and Ubuntu
```
sudo dpkg --add-architecture i386
sudo apt update
sudo apt-get install git rpm cmake g++-multilib libsdl2-dev:i386 libsdl2-mixer-dev:i386 libsdl2-ttf-dev:i386 libsodium-dev:i386 libsdl2-mixer-2.0-0:i386 libopusfile0:i386
```
### Compiling
```
git clone https://github.com/diasurgical/devilutionx
cd devilutionx
cmake -S. -Bbuild -DCMAKE_TOOLCHAIN_FILE=../CMake/32bit.cmake
cmake --build build -j $(nproc) --target package
```
## macOS
### Installing dependencies
Install [Xcode 9.4.1 and Xcode Command Line tools](https://developer.apple.com/download/more/?=xcode%209.4.1), this is the last version with **32 bits** support.

Note: Be sure that your to select the command line Xcode if you have more then one installed:
```
$ sudo xcode-select --switch /Applications/Xcode.app
```
Install the build tools using [Homebrew](https://brew.sh/):
```
brew install automake autoconf libtool
```
Get SDL2, SDL2_mixer, SDL2_ttf and Libsodium:
```
./xcode-build.sh --get-libs
```
### Compiling
```
./xcode-build.sh --build-libs
./xcode-build.sh --build-project
./xcode-build.sh --package
```
## Windows via MinGW
### Installing dependencies on Debian and Ubuntu

Download and place the 32bit MinGW Development Libraries of [SDL2](https://www.libsdl.org/download-2.0.php), [SDL2_mixer](https://www.libsdl.org/projects/SDL_mixer/), [SDL2_ttf](https://www.libsdl.org/projects/SDL_ttf/) and [Libsodium](https://github.com/jedisct1/libsodium/releases) in `/user/i686-w64-mingw32`. This can be done automatically by running `Packaging/windows/mingw-prep.sh`

```
sudo apt-get install cmake gcc-mingw-w64-i686 g++-mingw-w64-i686 wget git
```
### Compiling
```
git clone https://github.com/diasurgical/devilutionx
cd devilutionx
Packaging/windows/mingw-prep.sh  
cmake -S. -Bbuild -DCMAKE_TOOLCHAIN_FILE=../CMake/mingwcc.cmake ..  
cmake --build build -j $(nproc) --target package  
```

# Building for the native platform


## Linux
### Installing dependencies on Debian and Ubuntu
```
sudo apt-get install git rpm cmake g++ libsdl2-dev libsdl2-mixer-dev libsdl2-ttf-dev libsodium-dev
```
### Compiling
```
git clone https://github.com/diasurgical/devilutionx
cd devilutionx
cmake -S. -Bbuild ..
cmake --build build -j $(nproc) --target package
```
## macOS
Install the dependencies using [Homebrew](https://brew.sh/):
```
brew install cmake sdl2_mixer sdl2_ttf libsodium pkg-config
```
### Compiling
```
mkdir build
cd build
cmake ..
make -j$(sysctl -n hw.physicalcpu)
```
## Windows via MinGW
### Installing dependencies on Debian and Ubuntu

Download and place the 64bit MinGW Development Libraries of [SDL2](https://www.libsdl.org/download-2.0.php), [SDL2_mixer](https://www.libsdl.org/projects/SDL_mixer/), [SDL2_ttf](https://www.libsdl.org/projects/SDL_ttf/) and [Libsodium](https://github.com/jedisct1/libsodium/releases) in `/user/x86_64-w64-mingw32`. This can be done automatically by running `Packaging/windows/mingw-prep64.sh`

```
sudo apt-get install cmake gcc-mingw-w64-x86-64 g++-mingw-w64-x86-64 wget git
```
### Compiling
```
git clone https://github.com/diasurgical/devilutionx
cd devilutionx
Packaging/windows/mingw-prep64.sh  
cmake -S. -Bbuild -DCMAKE_TOOLCHAIN_FILE=../CMake/mingwcc64.cmake ..  
cmake --build build -j $(nproc) --target package  
```

# CMake arguments
## General
The default build type is `Debug`. This can be changed with `-DBINARY_RELEASE=ON`. Independently of this, the debug mode of the Diablo engine is always enabled by default. It can be disabled with `-DDEBUG=OFF`. Finally, in debug builds the address sanitizer is enabled by default. This can be disabled with `-DASAN=OFF`.
## mingw32
Use `-DCROSS_PREFIX=/path/to/prefix` if the `i686-w64-mingw32` directory is not in `/usr`.
