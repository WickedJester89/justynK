# 32-bit building on 64-bit platforms
## Linux
### Installing dependencies on Debian and Ubuntu
```
sudo apt-get install cmake g++-multilib libsdl2-dev:i386 libsdl2-mixer-dev:i386 libsdl2-ttf-dev:i386 libsodium-dev libsodium-dev:i386
```
### Compiling
```
mkdir build
cd build
linux32 cmake -DCMAKE_TOOLCHAIN_FILE=../CMake/32bit.cmake ..
linux32 make -j$(nproc)
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

Download and place the 32bit MinGW Development Libraries of [SDL2](https://www.libsdl.org/download-2.0.php), [SDL2_mixer](https://www.libsdl.org/projects/SDL_mixer/), [SDL2_ttf](https://www.libsdl.org/projects/SDL_ttf/) and [Libsodium](https://github.com/jedisct1/libsodium/releases) in `/user/i686-w64-mingw32`.

```
sudo apt-get install cmake gcc-mingw-w64-i686 g++-mingw-w64-i686
```
### Compiling
```
mkdir build
cd build
cmake -DASAN=OFF -DCMAKE_TOOLCHAIN_FILE=../CMake/mingwcc.cmake ..
make -j$(nproc)
```

# Building for the native platform
*Note: Since 64-bit builds are currently not in a playable state, it is advised to build in a 32-bit environment. Another possibility is a 32-bit build on a 64-bit system (see above).*
## Linux
### Installing dependencies on Debian and Ubuntu
```
sudo apt-get install cmake g++ libsdl2-dev libsdl2-mixer-dev libsdl2-ttf-dev libsodium-dev
```
### Compiling
```
mkdir build
cd build
cmake ..
make -j$(nproc)
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

# CMake arguments
## General
The default build type is `Debug`. This can be changed with `-DBINARY_RELEASE=ON`. Independently of this, the debug mode of the Diablo engine is always enabled by default. It can be disabled with `-DDEBUG=OFF`. Finally, in debug builds the address sanitizer is enabled by default. This can be disabled with `-DASAN=OFF`.
## mingw32
Use `-DCROSS_PREFIX=/path/to/prefix` if the `i686-w64-mingw32` directory is not in `/usr`.
