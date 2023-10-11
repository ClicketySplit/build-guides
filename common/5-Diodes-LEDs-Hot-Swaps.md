# Diodes
The surface mount pads of Leeloo are just large enough for SOD-123F diodes.  Leeloo rev1 was modified to be a little more accommodating…but not that much.  A fine tipped soldering iron will be required.

Why such small pads?  From my perspective, it helped keep the board’s design clean; not only saving space, but also while soldering the components—less solder.

Tip: Before soldering the diodes, consider unpackaging 10 at a time, and aligning them in the same direction as the shield’s diode direction.

You can identify the Cathode side of the diode by the white/grey bar that is laser enscribed on the one side.  Please see the following pictures.

If you line them up in the same direction, it helps reduce the potential of soldering the diodes the wrong way; and, it also helps keep track of all your diodes in case you sneeze; in case your cat jumps on the table; or, in case a gremlin takes one while you sip your IPA‡.

![Cathode Anode](images/v1.0/Cathode%20Anode.jpg)

To prepare for soldering, consider tinning either the cathode or anode side of the diode’s surface mount pads, but not both.  I like to tin the anode side, and finish with the cathode side; spotting for the diode’s index stripe or mark upon completing each position.

Another benefit of consistent tinning of one side is: it helps ensure that as you pull from the row of aligned diodes you’ve created, you reduce the risk of installing one backwards.

![Diodes and Tinning](images/v1.0/Diodes%20and%20Tinning.jpg)

Tip 2: carry this tip with you like a feather of knowledge in your cap.  As you progress with each soldered position, consider cleaning each position with IPA and a cotton swab.  Cleaning the area will remove the rosin left behind when the solder melts.  It keeps your board clean, and your OCD will thank you.

![Diodes Soldered](images/v1.0/Diodes%20Soldered.jpg)

# RGB LEDs

## Wired with QMK
If you choose to implement QMK with Elite-Cs, or Elite-Pis, you **MUST** solder the Bypass Jumper.

## Wireless or wired with ZMK
The next chapter: **Bypass Jumper** is a very important read.  This chapter explains the major changes from Leeloo v2 and Leeloo-Micro v1.

### TL;DR
If you choose to install the RGB LEDs with nice!nanos:
* be sure to install the MOSFETs and Resistors.
* be sure to install the 3 position SIP.
* **DO NOT** solder the Bypass Jumper.

# Hot Swaps
The approach for hot swaps is identical to diodes.  Select a side to tin, and be consistent all the way through each position.  Consider unpacking all that are required, and aligning them as neatly as your OCD will allow.

![Hot Swaps](images/v1.0/Hot%20Swaps.jpg)

### Box/MX Hot Swaps
Box/MX Hot Swaps are straight forward, they can only be installed one way.

### Choc Hot Swaps
Choc Hot Swaps, on the other hand, have a particular direction.  If you take a close look at an individual hot swap component, and align the Kailh logo so that it reads from right to left, you may notice, at the bottom right, there is a little tab.  You may also notice that if you look at the opposite end, the profile is tapered.  

When soldering the hot swaps, be mindful of these physical characteristics, and align them with the outline silkscreened on the shield itself.
