# Z80 Playground v1.2 - Providing a negative edge triggered NMI



## Preamble

Ideally an AND gate would be added, but seeing as there is limited real estate remaining, placing and routing a 7408 would be a nightmare.

What can be achieved with the remaining one NOR gate (7404), one invertor (7402), and one OR (7432) 

I could add two diodes, to make a wired-AND from the output of the NOR gate (thereby retaining the switch and the weird positively triggered externalNMI line, intact).

The other diode option would be to dispense with the NOR altogether, and just make a three input wired-AND.


----

What are the downsides of having a positively triggered NMI?

Consider this circuit for a Z80 based SBC.

I believe that the NMI handling was inverted in this manner, using a NOR, due to the limited gates left over, after the other various glue logic was designed using NOR, OR and NOT gates. Maybe there was also a reluctance to add a quad AND 7408 just for the NMI.

Nevertheless, this logic seems flawed.

For me, I can see three immediate downsides:

 - a delayed response to an NMI trigger – rather than the CPU seeing the NMI request immediately, it only "sees" it when NMI is released HIGH.
 - a periphal that waits for a response to NMI being brought low will be sitting there indefinitely
 - a pull up somewhere on the bus, on on a peripheral board, fighting the pull down resistor that is connected to the externalNMI line. Possibly the most serious, due to the current draw/drain?

However, how many peripherals would use NMI? Why is it on the bus? Doesn't only the user perform htis action in the case of a crah? INT, yes, is used by peripherals, obviously, but if the NMI is *only* going to either the momentary button on the board, or an exteranl NMI button on a case, for example, then the whole positively-edged trigger issue is a moot one.


Related: 

 - [How does the Z80 NMI edge detection work?](https://retrocomputing.stackexchange.com/questions/30781/how-does-the-z80-nmi-edge-detection-work) - good
 - [Z80 CPU and nested/reentrant NMI](https://retrocomputing.stackexchange.com/questions/23743/z80-cpu-and-nested-reentrant-nmi) - 50-50
 - [Can the Z80 Bus Request be used as an NMI?](https://retrocomputing.stackexchange.com/questions/25649/can-the-z80-bus-request-be-used-as-an-nmi) - meh




## Fixes

Note: `Z80_Playground (RCBUS80 RS4CUN) - RCBUS80r5cp2fixed4zc - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)` was an attempt using OR and active LOW, which obviously failed, but should be discarded.

### 2 layer

Z80_Playground (RCBUS80 RS2CUN) - RCBUS80r5gz9c - 54v - DRC_OK (CTS) (JMP)

Fix-> RCBUS80r5gz9d (ignore not done)

No! Better to derived from CUP, as this has recent PCB fixes (?list them), which were not done to the CUN variants

Z80_Playground (RCBUS80 RS2CUP) - RCBUS80r5gz9b - 54v - DRC_OK (CTS) (JMP)

Fix -> RCBUS80r5gz9be

Not easy, have to go right across the board, and back:

 - +3 via just for EXT_NMI
 (- +1 via for A4)
 - +5 via just for NOT-NOR
 - Total: 54+8 vias => 62 vias

No! Should have derived it from the correct and latest "extNMI routed" CUP:

Z80_Playground (RCBUS80 RS2CUP) - RCBUS80r5gz9bn - 56v - DRC_OK (CTS) (JMP)

Fix -> RCBUS80r5gz9bm

Not easy, have to go right across the board, and back:

 - +3 via just for EXT_NMI
 - +5 via just for NOT-NOR
 - Total: 56+8 = 64 vias!


Z80_Playground (RCBUS80 RT2CUP) - RCBUS80r5fz9bn- 56v - DRC_OK (CTS) (JMP)

Fix -> RCBUS80r5fz9bm

Not easy, have to go right across the board, and back:

 - +3 via just for EXT_NMI
 - +4 via just for NOT-NOR, but then CTS is in the way, blocking the final via - will need to find an alternative route.
 - +7 via just for NOT-NOR
 - Total: 56 + 10 = 66 vias!!!
 - Need to find a better way!?


Z80_Playground (RCBUS80 RT2CUN) - RCBUS80r5fz9bm - 66v - DRC_OK (CTS) (JMP)

Reduce vias: RCBUS80r5fz9bo


 - +3 via just for EXT_NMI
 - +4 via just for NOT-NOR
 - Total: 56 + 7 =  63 vias!!!
 - Should use new route on RS2
 - Had to shift C9

Maybe less vias, 2 or 3, for NOT-NOR, around the edge, using a circuitous route?

Z80_Playground (RCBUS80 RT2CUN) - RCBUS80r5fz9bo - 63v - DRC_OK (CTS) (JMP)

Reduce vias further: RCBUS80r5fz9bp

 - +1 via just for EXT_NMI
 - +4 via just for NOT-NOR
 - Total: 56 + 5 =  61 vias!!!

Z80_Playground (RCBUS80 RS2CUN) - RCBUS80r5gz9bm - 64v - DRC_OK (CTS) (JMP)

Reduce vias: RCBUS80r5gz9bo
 - +3 via just for EXT_NMI
 - +4 via just for NOT-NOR
 - Total: 56 + 7 =  63 vias!!!
 - Had to shift C9

Maybe less vias, 2 or 3, for NOT-NOR, around the edge, using a circuitous route?

Z80_Playground (RCBUS80 RS2CUN) - RCBUS80r5gz9bo - 63v - DRC_OK (CTS) (JMP)

Reduce vias further: RCBUS80r5gz9bp

 - +1 via just for EXT_NMI
 - +4 via just for NOT-NOR
 - Total: 56 + 5 =  61 vias!!!

### 4 layer

Z80_Playground (RCBUS80 RS4CUP) - RCBUS80r5cp2fixed4zbn - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix : RCBUS80r5cp2fixed4zbm

Long circuitous blue routes


Z80_Playground (RCBUS80 RT4CUP) - RCBUS80r5cp2fixed3zbn - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix : RCBUS80r5cp2fixed3zbm

Long circuitous blue routes

Z80_Playground (RCBUS80 RT4CUN) - RCBUS80r5cp2fixed3zbm - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Shorter? (green route, to EXT_NMI): RCBUS80r5cp2fixed3zbo

Probably about the same. NMI is not that important to spend a lot of time and effort on.


## Conclusion: 2 layer or 4 layer?

An additional 7 vias to boards already containing 54 or 56 vias would be an increase of over 10%! However, taking into consideration the work done to reduce the increase from 10 to just 5 additional vias, for such an important change, and seeing as an increase of 5 vias is *less* than 10%, then the increase is *not* as drastic as it might first appear to be.

An additional +7 vias might prove that the 2-layer board should be discarded, in favour of the original Squire 4-layer board, but +5, not so much? If the use of 4 layers was intended for the original, then why is the RCBUS80 board relying upon 2-layer? For cost, but what is the difference in cost?

However, seeing as the subsequent RAM disable fix, see [Z80 Playground v1.2 - Adding RAM disable.md](Z80 Playground%20v1.2%20-%20Adding%20RAM%20disable.md), does not add an new vias, then, on average, it could be taken as a "win". In which case, they is no *real* need to dismiss the 2 layer boards out-of-hand, entirely.