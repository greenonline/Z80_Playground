# Z80 Playground v1.2 - Inverting the NMI (for RCBUS) - negative edge trigger


## Preamble

The Z80 Playground has a positive edge triggered NMI, which is incompatible with the RCBUS, and Z80 peripherals, in general. It is not required for the Squires board as it isn't original, although the negative-edge trigger option *could* be provided. The MJ/GOL_ variant can also offer the variant.

Note: The RCBUS40 board is not affected by this issue, as NMI is not routed to the bus.

## Notes

Add a three pin jumper so one board can provide both positive and negative?

   - Can use the remaining inverter? But requires long routing, and vias?
   - Use OR instead of NOR and pull up instead of pull down
     - The logic won't work, logic OR is not correct! Wired-OR, is it AND? AND is the same as active low wired OR
     - Nope! Wrong logic, use inverter on extNMI and NOR, and pull ups(???).
   - There is a NOR, and an OR and a NOT gate. Would an OR with inverted inputs help? No, but a NOR with an inverted /NMI input would work! No it does not!
     - TBH, it doesn't look correct at all. Why was it done this way, to reuse components?
   - Is the externalNMI actually routed on the RCBUS? Or is it /NMI itself? If /NMI then it needs a pull up resistor
     - No, it is not, on RCBUS80, /NMI is routed to the bus, which could cause a contention short - FIXED!
     - Have another variant where external NMI is routed? - FIXED!
       - Or does it matter? (Yes, it does)
   - RCBUS40 is not affected by this issue, as NMI is not on the bus.

   - (Yet) Another variant of the board P/N - positive negative edge NMI!

TODO: Does it matter about the positive edge, if /NMI is routed to the bus and the "external NMI" is ignored anyway?
 - Yes, because there could be contention between the NOR connected to the NMI and whatever else, on the bus, is connected to NMI.


 - [Why is it called Wired-OR when it is functioning as Wired-NOR?](https://electronics.stackexchange.com/questions/490308/why-is-it-called-wired-or-when-it-is-functioning-as-wired-nor)
 - [Wired logic connection](https://en.wikipedia.org/wiki/Wired_logic_connection#The_wired_OR_connection)

NOR (with active HIGH inputs)

| A | B | O = (A /+ B) |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

OR

| A | B | O = (A + B) |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

OR with both inverted inputs

| A | B | O = (/A + /B) |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

NOR with an input NMI `B` to single NOT B (active low, tied high) and manual input `A` (active low, tied high)

| A | B | O = (A /+ /B) |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

Not a solution: 

 - manual input only works if external NMI is active.
 - extNMI works ok, irregardless of manual
 - If manual input not pressed then interrupt


It *is* a solution if input NMI `B` to single NOT (active low, tied high) and manual input `A` (active high, tied low).

Alternative: Need pull-up and two diodes for wired-AND.

Queries:

 - Can NOR gate function as a diode, or does it need a diode?
   - Of course it needs a diode, to avoid current draw, and contention
 - What resistor value: [Wired AND, OR gates and compatibility with TTL/CMOS fan-out](https://electronics.stackexchange.com/questions/521591/wired-and-or-gates-and-compatibility-with-ttl-cmos-fan-out), 1k?
 - Do we need to use open collector gates?
   - No, not if we are using diodes. If we had open collector gates, then we would only need a resistor.

## Pull-ups

 - Pull-up resistors for NMI, INT, BUSRQ, WAIT, DMA? As per the Z180 CPU board, [Z80 Retrocomputing 18 – Z180 CPU Board for RC2014](https://www.smbaker.com/z80-retrocomputing-18-z180-cpu-board-for-rc2014)
   - Unlikely that there is room
   - Why?
   - Are the necessary?
   - Should they be on the backplane instead of per board?
   - TODO: Check [RCBUS specification](https://smallcomputercentral.com/rcbus/)
     - `/INT` should have a pull-up resistor - do for RCBUS variants
   - Already pulled up! INT, BUSRQ and WAIT
   - [Z80 RC2014 schematic](https://8b8bf43264c2f150841a.b-cdn.net/wp-content/uploads/2017/04/Z80-CPU-Rev-1_3.pdf) shows: INT, NMI, BUSRQ and WAIT pulled up
   - Just need to add NMI
   - [Question about pull-up resistors for the INT, NMI, BUSRQ, and WAIT pins.](https://www.reddit.com/r/Z80/comments/175h7yn/question_about_pullup_resistors_for_the_int_nmi/)

From [Z80 CPU v2.1](https://rc2014.co.uk/modules/z80-cpu-v2-1/)

> Some signals, such as INT, BUSRQ, WAIT and NMI need to be pulled high for normal operation.  The original CPU Module did this with links to the 5v line – however, this meant that modules that needed to use these, such as the SD Memory Dump Module, risked damage to the CPU or module.  The v2.1 CPU Module overcomes this by using 10k resistors to pull the signals high, which allows them to be safely pulled low if required.

The [Z80 data sheet](https://www.zilog.com/docs/z80/um0080.pdf) says only BUSRQ and INT require pull-ups, and then only for wired-OR applications. Maybe it is OK.

it *is* OK as it is, as there is a weird NMI circuit with a NOR that I had forgotten about.

However, this "weird" NMI circuit inverts the edge upon which it is triggered, so change will be required for the RCBUS variants. Not required for the Squires board as it isn't original, although the negative-edge trigger option *could* be provided...

MJ/GOL_ variant can also offer the variant.

