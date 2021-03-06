# GUIslice library - Examples for LINUX #
This folder contains examples for LINUX-based devices using **SDL**
such as the **Raspberry Pi** or **Beaglebone Black**.

### Installation ###
In order to run the SDL1.2 / SDL2 examples, it is important that the SDL
graphics driver is installed first. A detailed installation guide has been
provided at: https://www.impulseadventure.com/elec/rpi-install-sdl.html

If touch support is required, then the **tslib** library should be
installed. A detailed installation guide has been provided at:
https://www.impulseadventure.com/elec/rpi-install-tslib.html

For the purposes of diagnostics, a simple test of the basic SDL graphics driver has been provided:

**SDL1.2**:
~~~
# Demonstration using SDL1.2
make test-sdl1
sudo ./test-sdl1
~~~

**SDL2**:
~~~
# Demonstration using SDL2
make test-sdl1
sudo ./test-sdl1
~~~

### Compiling ###
The examples in this folder are designed to be compiled using the provided `Makefile` at
the command-line. It is assumed that SDL and the optional touch library has been installed.
Detailed installation notes available at: 

~~~
make gslc_07
sudo ./gslc_07
~~~


### Device Support ###
Sample code in these examples are intended for the following device platforms:
- Raspberry Pi 1 / 2 / 3
- Beaglebone Black
- and other LINUX platforms

### Font Files ###
Most of the example files require the use of a font resource. By default, the examples use the **noto** font which is usually installed in the following location: `/usr/share/fonts/truetype/noto/NotoSans-Regular.ttf`. Please confirm that this font file exists at this location (or update the example's font resource path accordingly) before running the examples. If this font isn't already installed in your system, you may be able to install it with `sudo apt-get install fonts-noto`.

Note that earlier versions of GUIslice defaulted to the **droid** font, but this has changed since recent linux distributions no longer include **droid**.

### Resource Files ###
Some examples (eg. `glsc_ex03`) are intended to demonstrate image loading from SD cards.
In order to support these functions, one needs to ensure:
- Resource files from the `/res` folder are copied into the root of the SD card
- SD card support is enabled in `GUIslice_config_linux.h` (via `#define GSLC_SD_EN 1`)
