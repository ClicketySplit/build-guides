# Quality Assurance
As you progress through testing, you may run into situations where functionality does not happen as anticipated.  This chapter will cover some typical problems and potential solutions.
## Test Each Switch
Having your firmware flashed to your MCUs, before this step, helps with QA tremendously—predictable use cases.  The simplest way to test your keyboard is to open a text editor and activate each switch.  Hopefully, based on your keymap, each switch that you've programmed will show up on screen—either by character, or by action.

## Test Each Rotary Encoder
If you've installed an EC11K or EC11N on your Leeloo, you should be able to press down on it to activate the switch.  Hopefully the character, or action is activated when actuated—that was a little practice of alliteration.

If the installed rotary encoder does not respond, review the configuration file, and ensure the option for rotary encoders has been uncommented.  If a change was required, save, recompile, and flash the MCUs.

### ZMK Implementations
```
# Uncomment these two lines to add support for encoders
CONFIG_EC11=y
CONFIG_EC11_TRIGGER_GLOBAL_THREAD=y
```

### QMK Implementations
Rotary Encoders are enabled by default.

## Test Each Layer
If all switches and rotary encoder actions are working, it's time to go through the process of verifying each key that you've configured in your keymap.  Methodically validate each layer by confirming each switch.

## Click, click, click...nothing.
Sometimes a switch doesn't activate; no worries.  Consider the following:
* Have a look at the hot swap, and the diode associated to the switch.
   * If it doesn't look good, try reflowing the joint.
* Tap the switch above, below, to the left, and right.
   * If the switches around the current switch also fail, it may be because the row or column of switches may have a cold solder joint on either the hot swap or diode.
* If all the hot swaps and diodes look good, have a look at the MCU sockets, verify that each socket position and pin have a good solder joint as well.

## Displays
If you're using nice!view or OLED Displays, confirm that the configuration line item has been activated.  If not, recompile with the configuration change, flash the MCUs, and you should immediately see the displays light up.

### ZMK Implementations
Open the leeloo.config, or Leeloo_micro.config file and ensure the following line:
```
# Uncomment the following line to enable the OLED Display or nice!view Display
CONFIG_ZMK_DISPLAY=y
```

### nice!view Displays
In the case of nice!view displays, have a look in the leeloo.keymap, or leeloo_micro.keymap file, and ensure that the following section has been uncommented.

```
/*
 * Assign the cs-gpios pin to 4.
 * Uncomment these next few lines if implementing nice!view Displays.
 */
nice_view_spi: &spi0 {
  cs-gpios = <&pro_micro 4 GPIO_ACTIVE_HIGH>;
};
```

After uncommenting the three lines, try recompiling each side, flashing each MCU, and hopefully the display information shows up.

When compiling for nice!views, ensure the following paramters when defining the DSHIELD paramter itself.  Here is an example for Leeloo-Micro:
```
-DSHIELD="leeloo_micro_rev2_left nice_view_adapter nice_view"
-DSHIELD="leeloo_micro_rev2_right nice_view_adapter nice_view"
```

Full command:
```
west build -d build/left -p -b nice_nano_v2 -- -DSHIELD="leeloo_micro_rev2_left nice_view_adapter nice_view"
west build -d build/right -p -b nice_nano_v2 -- -DSHIELD="leeloo_micro_rev2_right nice_view_adapter nice_view"
```

### QMK Implementations
QMK implementations have OLED Displays on by default, in the info.json file.
```
  "features": {
    "extrakey": true,
    "oled": true
  },
```

If they do not, have a look at the sockets and pins; ensure good connections; reflow if necessary.

## Chapters
Next: [Chapter 18: The Fruit](18-The-Fruit.md) \
Previous: [Chapter 16: Switches and Encoders](16-Switches-Encoders.md) \
Chapters: [Table of Contents](README.md) \
Home: [Index](/README.md)
