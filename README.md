![Leeloo](https://github.com/ClicketySplit/build-guides/blob/main/leeloo/images/gallery/Leeloo-v2-ZMK.jpg)

# Build Guide
Leeloo is available in two different form factors and may be configured in many ways.  Within this documentation, you'll find a base build guide, which will take you through the common process and steps to build Leeloo and Leeloo-Micro.

Leeloo v2.1 and Leeloo-Micro v1.1 have been revised to be more consistent amongst each other.  Albeit, their circuitry and components have changed, their shape and dimensions have not.

>    **What changed?**
>    1. Mill-Max Receptacles were used for socketing nice!view and OLED Displays.
>
>       To simplify, Mill-Max Pins are soldered to the PCB and serve as the male component to the SIP socket that is soldered to the nice!view or OLED Display.
>
> 
>    2. Circuitry was added to support the [Experimental: Automatic power domain handling for displays/RGB](https://github.com/zmkfirmware/zmk/pull/1775) branch currently in draft by **Pete Johanson**.
>
>       Added two components: MOSFET and Resistor, along with a Solderable Bypass Jumper, which can be used if RGB LEDs are not installed.
>
>       **Note:** nice!view Displays are currently unsupported; yet, OLED Displays are.  Hopes are that nice!view Displays will be supported soon, we will keep an eye on the development, and update this guide as soon as we learn more.
>
>       We will also keep the Leeloo and Leeloo-Micro branches up to date to support the evolutionary changes.

## Typical Workflow
Generally speaking, building Leeloo and Leeloo-Micro will be similar:
* Review Components
* Prepare Firmware
    * ZMK | Leeloo and Leeloo-Micro
    * QMK | Leeloo Only
    * Flashing the MCU
* Cleaning the Shields
* Diodes
* RGB LEDs†
* Hot Swaps
* MOSFETs and Resistors or Solderable Bypass Jumper
* MCU SIPs
* MCU Pins
* MCU Installation
    * Remove MCU
* Receptacles
* Reset Switches
* TRRS Jacks† | Leeloo Only
* On/off Switches†
    * Bridging
* nice!view Pins or OLED Pins
* Case
* Switches Part I
* nice!view or OLED SIPs
* Batteries†
* Insert MCU
* Switches Part II
* Rotary Encoder(s)†
* Quality Assurance
* Bottom Plate
* Keycaps

† Optional steps.

## Feedback
We hope you find this build guide helpful.  If you find an error, or have any recommendations to help make this guide better, please [contact us](https://clicketysplit.ca/pages/contact-us), so we may be able to make the modifications.

Thank you,

Clickety Split  
For the love of split keyboards.
