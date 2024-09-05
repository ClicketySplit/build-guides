# Preparing the Firmware
Both ZMK and QMK have excellent documentation to get you started with setting up the build environment.

Consider building and flashing the default firmware for Leeloo, or Leeloo-Micro onto your microcontrollers.  By having the firmware compiled, and installed you can ensure that your build environment and keymap are set up and error free; and, as you progress through quality assurance, you have a baseline keymap to test against.

## Flashing the Microcontrollers
When flashing nice!nano, and Elite-Pi microcontrollers, they follow the same steps:

1. Connect the Left or Right side to a USB-C cable.
2. Double-click the reset button at the bottom of Leeloo, or Leeloo-Micro with a blunted toothpick to place the MCU into bootloader mode.
3. Drag and drop the .uf2 file to the root of the microcontroller's file system.
4. Repeat for the second side.  When flashing nice!nanos, ensure that the proper .uf2 file is copied to its corresponding side.


When flashing Elite-C microcontrollers, they follow a slightly different process:

1. Connect the Left or Right side to a USB-C cable.
2. Double-click the reset button at the bottom of Leeloo, or Leeloo-Micro with a blunted toothpick to place the MCU into bootloader mode.
3. Issue the `qmk flash` command to flash the firmware.
4. Repeat for the second side.  The same .hex file can be used for both sides.


### Keeping track of the Left and the Right Microcontrollers
When flashing your microcontrollers, be sure to keep note, or physically separate them as Left and Right.  It will help when installing them in the chapter: ***MCU Installation***.

## ZMK
ZMK's documentation provides two ways to build firmware.

### GitHub Actions
If you would like to build your firmware in the cloud, follow the instructions: 
[Installing ZMK](https://zmk.dev/docs/user-setup).

> **NOTE** \
> Because the firmware for Leeloo v2.1 and Leeloo-Micro v1.1 are based on the [Experimental: Automatic power domain handling for displays/RGB #1775](https://github.com/zmkfirmware/zmk/pull/1775) branch; GitHub Actions may not be used until the feature becomes part of the main ZMK branch.  Consider using the following Toolchain Setup method.

### Toolchain Setup
If you would like to build your firmware on your local machine, follow the instructions: [Development > Toolchain Setup](https://zmk.dev/docs/development/setup).

### Firmware Branches
Configurations without RGB LEDs can leverage the main branch:
[Leeloo rev2](https://github.com/zmkfirmware/zmk/tree/main/app/boards/shields/leeloo), or [Leeloo-Micro](https://github.com/zmkfirmware/zmk/tree/main/app/boards/shields/leeloo_micro).

> **IMPORTANT** \
> The ***current*** main branch supports RGB LEDs, and nice!view displays; however, the ***Bypass Solderable Jumper*** must be used.  As an important note, ***the battery capacity will drain very quickly.***

### Power Domains
Leeloo v2.1 and Leeloo-Micro v1.1 configurations with RGB LEDs should consider using the following branches, depending on your version of Leeloo:

* [Leeloo v2.1 Power Domains | leeloo_rev3](https://github.com/ClicketySplit/zmk/tree/clickety_split_series_zmk_v3.5_power_domains/app/boards/shields/clickety_split_leeloo), or
* [Leeloo-Micro v1.1 Power Domains | leeloo_micro_rev2](https://github.com/ClicketySplit/zmk/tree/clickety_split_series_zmk_v3.5_power_domains/app/boards/shields/clickety_split_leeloo_micro) branch.

This will ensure proper power management and ensure long standby times while Leeloo is in sleep mode—power is completely cut to the RGB LEDs.

#### Using GitHub Actions with a ZMK fork
If you use either of the above branches and want to build your firmware with GitHub Actions, you will need to set up your zmk-config repo manually as the ZMK Installation steps rely on a shell script that's incompatible. Here are the steps to manually set up a repo with custom keymap files and a GitHub Actions workflow that will build your firmware files:
1. Create a new GitHub repo
2. Copy this zmk-config folder into your repo
3. Update the `.conf` and `.keymap` file as desired
4. Add a file `.github/workflows/build.yaml` with the contents:
```
on:
  push:
    paths:
      - "config/**"
  pull_request:
    paths:
      - "config/**"
  workflow_dispatch:

jobs:
  build:
    uses: ClicketySplit/zmk/.github/workflows/build-user-config.yml@clickety_split_series_zmk_v3.5_power_domains
```
5. Then, you can trigger the workflow and [download the `.uf2` files](https://zmk.dev/docs/user-setup#download-the-archive). Alternatively, the workflow should run every time you update a file in the `/config` folder.

## QMK
QMK's documentation provides instructions for Windows, Mac OSX, Linux, and FreeBSD.
[QMK Firmware: Tutorial > Setup](https://docs.qmk.fm/#/newbs_getting_started)

### Leeloo v2.1 Firmware
[Leeloo v2.1, or revision 3](https://github.com/qmk/qmk_firmware/tree/master/keyboards/clickety_split/leeloo).

## Chapters
Next: [Chapter 4: Mise en place](4-Mise-en-place.md) \
Previous: [Chapter 2: Components](2-Components.md) \
Chapters: [Table of Contents](README.md) \
Home: [Index](/README.md)
