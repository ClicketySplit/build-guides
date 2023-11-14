## Preparing the Firmware
Both ZMK and QMK have excellent documentation to get you started with setting up the build environment.

Consider building and flashing the default firmware for Leeloo, or Leeloo-Micro onto your microcontrollers.  By having the firmware compiled, and installed you can ensure that your build environment and keymap are set up and error free; and, as you progress through quality assurancee, you have a baseline keymap to test against.

## Flashing the Microcontrollers
When flashing nice!nano, Elite-C, and Elite-Pi microcontrollers, they follow the same steps:

1. Connect the Left or Right side to a USB-C cable.
2. Double-click the reset button at the bottom of Leeloo, or Leeloo-Micro with a blunted toothpick.
3. Drag and drop the .uf2 file to the root of the microcontroller's file system.
4. Repeat for the second side.  When flashing nice!nanos, ensure that the proper .uf2 file is copied to its corresponding side.

### Keeping track of the Left and the Right Microcontrollers
When flashing your microcontrollers, be sure to keep note, or physically separate them as Left and Right.  It will help when installing them in the chapter: ***MCU Installation***.

## ZMK
ZMK's documentation provides two ways to build firmware.

### GitHub Actions
If you would like to build your firmware in the cloud, follow the instructions: 
[Installing ZMK](https://zmk.dev/docs/user-setup).

### Toolchain Setup
If you would like to build your firmware on your local machine, follow the instructions: [Development > Toolchain Setup](https://zmk.dev/docs/development/setup).

### Firmware Branches
Configurations without RGB LEDs can leverage the main branch:
[Leeloo rev2](https://github.com/zmkfirmware/zmk/tree/main/app/boards/shields/leeloo), or [Leeloo-Micro](https://github.com/zmkfirmware/zmk/tree/main/app/boards/shields/leeloo_micro).

> [!IMPORTANT] \
> The ***current*** main branch supports RGB LEDs, and nice!view displays; however, the ***Bypass Solderable Jumper*** must be used.  As an important note, ***the battery capacity will drain very quickly.***

### Power Domains
Leeloo v2.1 and Leeloo-Micro v1.1 configurations with RGB LEDs should consider using the following branches, depending on your version of Leeloo:

* [Leeloo v2.1 Power Domains](https://github.com/ClicketySplit/zmk/tree/leeloo_v2.1_power_domain/app/boards/shields/leeloo), or
* [Leeloo-Micro v1.1 Power Domains](https://github.com/ClicketySplit/zmk/tree/leeloo_micro_v1.1_power_domain/app/boards/shields/leeloo_micro) branch.

This will ensure proper power management and ensure long standby times while Leeloo is in sleep mode—power is completely cut to the RGB LEDs.


## QMK
QMK's documentation provides instructions for Windows, Mac OSX, Linux, and FreeBSD.
[QMK Firmware: Tutorial > Setup](https://docs.qmk.fm/#/newbs_getting_started)

### Leeloo v2.1 Firmware (Develop)
[Leeloo v2.1, or revision 3](https://github.com/ClicketySplit/qmk_firmware/tree/develop/keyboards/clickety_split/leeloo), is currently merged into the Develop branch.  The changes should be merged into Main in the near future.

## Chapters
Next: [Chapter 4: Mise en place](4-Mise-en-place.md) \
Previous: [Chapter 2: Components](2-Components.md) \
Chapters: [Table of Contents](README.md) \
Home: [Index](/README.md)
