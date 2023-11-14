## Why use the Bypass Jumper?
The bypass jumper is used to—quite literally—bypass the circuitry added to cut power from the VCC pin to the RGB LEDs, by virtue of the, at present, experimental implementation of Power Domains.

If your implementation of Leeloo will be wired and will also include RGB LEDs.  ***You must solder the bypass jumper.***

If your implementation of Leeloo, or Leeloo-Micro is wireless and will also include RGB LEDs, you have a choice:

* Ignore installation of the MOSFETs and Resistors, and solder the bypass jumper—this option ***will leak*** battery capacity.

* Install the MOSFETs and Resistors, and ignore the bypass jumper; leverage the Power Domain feature—battery capacity is preserved while Leeloo or Leeloo-Micro is in sleep mode.

## Installation of the MOSFETs and Resistors
1. Tin one of the three SMD pads of the MOSFET location.
2. Tin one of the two SMD pads of the Resistor location.
3. Tack the MOSFET onto its position.
4. Tack the Resistor onto its position—the **blue** side is up; and [I like to] orient the wider of the two solderable ends towards the top of the board.
5. Complete soldering of the remaining SMD pads.
6. Clean each SMD pad with IPA and a cotton swab.

> Take a moment to clean each location with 99% IPA and a cotton swab.
