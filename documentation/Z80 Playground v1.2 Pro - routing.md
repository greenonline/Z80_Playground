# Z80 Playground v1.2 Pro - routing

## Preamble

The Z80 Playground v1.2 routing, as derived from the images shown in the video, [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them](https://www.youtube.com/watch?v=MaolTlk7XKM).

In retrospective, this wasn't overly difficult, just time consumming. Although I had two major hurdles: forgetting to place the mounting holes before finialising routing, and; the orientation of the TTL serial connector.

The first issue was solved by some manual re-routing. The same for the TTL serial connector. However, in the latter case, the orientation of the TTL serial connector in original layout by John Squires suited *his FTDI module*, as shown in [Flow Control for UART Serial communication between Z80 Playground and a PC](https://www.youtube.com/watch?v=RFxSKGnuisE) at [8:56](https://www.youtube.com/watch?v=RFxSKGnuisE), which has less common *reversed ordering* of the connectors. So, most fortuitously, it transpired that *my* original orientation of the connector was suitable for the more usual clone red FTDI module.

In addition, placement of the crystals required numerous iterations, and re-routing, although these were mostly down to poor initial placement decisions, and then further indecision.

### The Pro

A version for professionals!


## Notes

### Routing

The routing proved tricker than I expected, mostly as I had presumed that there was an autoroute feature in KiCAD 6 – I was mistaken... Even PCB design software back in the 80's had autoroute, so gawd knows why KiCAD 6 doesn't! Too early a version, I guess.

These four screenshots, showing the traces, were taken to use to replicate the routing:

[![Z80 Playground v1.2 - PCB front#1][6]][6]

[![Z80 Playground v1.2 - PCB front#2][7]][7]

[![Z80 Playground v1.2 - PCB front#3][8]][8]

[![Z80 Playground v1.2 - PCB rear#1][9]][9]

TOP TIP: Use rear for near-as-possible verticals, and front for near-as-possible horizontals, only – it makes life a lot easier. Use vias to "zig-zag" across the board, thereby avoiding long diagonals, on any plane, at all costs.

After partially routing the GOL variant in my own manner, I decided to add the footprints to the Squires and RBUS variants, and to route them manually from new. For the Squires variant, I diligently copied the traces shown in the photos above, and for the RBUS variant I used the better of the two – TODO: XXX = GOL or Squires???

#### Freerouting

[Freerouting](https://github.com/freerouting/freerouting) is, apparently, a standalone ultiity that can take KiCAD 6 PCB files and auto-route them.

Unfortunately, I couldn't get Java (JRE) running correctly on my Catalina Mac, to get the Java version of Freerouting to run – the native Mac version is ARM only.

I managed to get [Freerouting 1.9.0](https://github.com/freerouting/freerouting/releases#release-v1.9.0) downloaded and running. In KiCAD PCB Editor, once the component have been layed out then File>Export>Specctra DSN..., Save, and then in Freerouting open the file, delete any traces and Autoroute. 

##### General synopsis

Routing should be done by around 12 or 14 passes, sometimes as low as 8 – which takes around a minute a pass, ten minutes is the usual routing time. If not done by 20 passes, then the autorouter has got stuck.

Each optimisation pass takes around 10 minutes. Between 10 up to 20 optimisation passes may be required. 

Total time can range from 1 hour to 8 hours.

##### Initial attempts

# A new start... a new hope

#### Pro pga01

Cloned from RCBUS80r5fz9

XTALs moved much closer (i.e. next to) the IC pins

 20:08 - ~10 passes (7 mins), 112 vias, #1 112-> 100->??, #2 ??->98->96->?? (20:27), #3 >?? -> 94 (20:39), #4 94->93 (20:48), #5 93 (20:55), #6 93 (21:03), #7 93 (21:11), #8 92 (21:19), #9 92 (21:26), #10 92 (21:33), #11 92 (21:43), #12 92->91->90->89 (21:52), #13 89 (22:02), #14 89 (22:13), #15 89 (22:19), #16 89 (22:28), #17 89 (22:38), end 89 (22:46).


TL: 8.03 M -> 7.982 M -> 7.978 M -> 7.959 M -> 7.938M -> #12 7.953M-> 7.955-> 7.967 -> #13 7.959 M -> #15 7.951 M

Not a promising start. The largest concenration of the vias is under the CPU.

##### Solutions:

Move U5 in from edge of board, to prevent via for side line?
Move Bus up from edge of board?
 - Can not, hole in the way
   - Maybe move hole up a notch – it *doesn't have* to match the other boards, does it?
 - Move jumpers so that /a10 and /notROM are short traces? 
 - Maybe leave layout as pre non-pro RCBUS80 RT2 and just add CTS – to start with, then later move caps individually?
 - Swap bus to forward? (last resort?)

#### Pro pgb01

Cloned from pga01

Radical layout shift

Bypass caps moved to next to IC GNDs
Moved U5 in from edge of board, to prevent 2 vias for side line (maybe not needed as optimisation ultimately removed the 2 vias, if fails then move back to edge)
Added CTS!


22:47 - 10-12 passes, failed on 2?, nope! #16 ( 22:54), 120 vias, #1 120 -> 100, #2 100 ->  91 (23:05), #3 91 (23:16), #4 91 (23:25), #5 91 (23:34), #6 91 (23:42), #7 91 (23:52), #8 91->90 (24:01), #9 90 (00:13), #10 90 (00:24), # 11 90 	(00:34), #12 90 (00:52), end  90 (00:52).


TL: 8.334M -> #3 8.322 M -> #8 8.234 M

Even worse and high trace length!!! Probably because caps are in the way of the buses between the four main ICs - they were better off out of the way on the edge of the board,, not between the ICs.




### Pro pGc01

Cloned from RCBUS80r5fz9


Changed only addition of CTS


00:53 - 8 passes (00:58), 105 vias, #1 105->92, #2 92 ->84 (01:18?),  end 68 (p748?)


### Pro pGc02
Cloned from pGc01
Rerun - unchanged

08:09 - 8 passes (08:14), 105 via, #1 105->102, #8 75 (09:09), #9 73 (09:14), #10 72 (09:21), #11 72 (09:28), #12 72 (09:34), #22 69 (10:22), #23 68(10:28) , #24 68 (10:34)  #25 68 (10:38), end 68 (10:57)


Exactly the same, waste of time!

### Pro pGd01

Cloned from pGb01

Shifted up bus, but did not move holes


11:02 18 passses (11:11), 128 via, #1 128->118, #4 91 (11:54), #5 91 (12:02),  #6 91->90 (12:13), #7 89 (12:26), #8 89 (12:37) #9 87 (12:47), #14 86 (13:41), end 86 (14:00)

TL: #4 8.356 M

Started off even worse! Each adjustment causes further regresssion! Shifting up doesn't seem to have helped much. End result is a bit better though, best, so far...

Maybe shift up one more notch, for two traces?

### Pro pGd02

Cloned from pGd01

Moved bus up another notch
Also shifted up HL3 and HL4, one notch
Also shifted up U6 and U8, one notch

14:05 - 15 passes (14:12), 101 via, #1 101->94, #2 ??->89?->88->86->?? (14:23), #3 ??->81->78 (14:36), #4 78->76 (14:46), #5 76->75 (14:52), #6 75 (14:59), #7 73 (15:08), #8 73 (15:14), #9 73 (15:23), #10 73, #11 73 (15:34), #12 73 (15:41) end 73 (15:46)

TL: 8.151 M

A very promising start, good progression. Approaching that of pGc01. The extra lines, under the bus are definitely being used.


#### Pro pGd03

Cloned from pGd02

UART xtal caps to the left
R9 moved up


16:00 - 12 passes failed on 4 
16:06 (accidently stopped, and then restarted) - 16 passes failed on 6 then 32 passed failed on 4

1616 - ~16-32 passes, failed on 4 traces (16:26), vias, #1, end

Abandonned

Maybe moving R9 was a mistake?



#### Pro pGd04

Cloned from pGd02

Moved only UART XTAL caps to left of XTL. Left R9 were it was.

16:28 - 15 passes failed on 8 (), vias, #1, end.
16:35 - 15 passes failed on 8

Abandonned

#### Pro pGd05

Cloned from pGd03

Moved power cap, r16 and led to the right column
Moved UART crystal, cap and r7 to bottom of UART, away from data bus between RAM, and ROM and UART


16:47 - 13 passes failed on four (), via, #1 , end
17:07 pass 5115 failed on 2 (17:22)

Abandonned

#### Pro pGd06

Cloned from pGd05


Moved UART XTAL next to bottom of UART, caps back to the right (again)

17:36 13 passes, 101 vias (17:42), #1 101->89 , #2 89->88 (17:55), #3 86, #4 86->80 (18:12), #5 80 (18:20) #6 80-79 (18:33) #7 79->78 (18:44), #8 78->77 (18:50), #9 77->76 (19:00), #10 76 (19:08), #11 76 (19:17), #12 76 #13 76 (19:52), #14 76 (20:00), #15 76 (20:10), #16 76 (20:17), #17 76 (20:24), end 76 (20:38)


TL: 8.217 -> 8.147 -> 8.188M

Another promising start, very good reduction in first pass (better than pGd02), then quickly fell off the rails.


#### Pro pGd07

Cloned from pGd06

Moved R9 back down, right next to U8's associated pins

20:39 - passes #10 stuck on 6, #14 stuck on 2, ~16 passes,  98 via (20:45), #1, 98->84, #2 84->78 (20:54), #3 78->77 (21:01), #4 77->74 (21:10), #5 73 (21:20), #6 71->70 (21:26), #7   70 (21:34), #8 70->68 (21:40), #9 68 (21:46), #10 68->66 (21:52), #11 66 (21:58), #12 66->64 (22:03), #13 64 (22:09), #14 64 (22:16), #15 64 (22:22), #16 64->63 (22:29), #17 63 (22:36), end 63 (22:43) 

TL: 8.34 M -> end 8.317

A good start, and excellent progress, easily surpassing that of the "CTS only added" pGc01 (68).

#### Pro pGd08

Cloned from pGd07

UART cap next to UART GND

22:42 - 22:48 failed on 4 ~#20

22:49 - 22:53 failed on 4 ~#11
07:20 - 07:29 failed on 4 ~54

Crazy that it does not route as only cap moved slightly. Was pGd07 a fluke?

Abandoned.

Solution?: Easier to manually move the cap cloning from from pGd07 -> pGd07a

#### Pro pGd07a

Cloned from pGd07

Manually moved UART cap


Not needed as pGd09 is better 

#### Pro pGd07b

Cloned from pGd07a

Silkscreen errors fixed.

Really this should still be 07a as no components moved.


### pGd08a

Cloned from unroutable pGd08

Moved UART cap to lower left sie, xtal away to the bottom, not right next to UART

07:33 - 07:39 at 10 passes failed on 2 traces
07:39 - 07:45 at 11 passes failed on 2 traces

Abandonned

### Pro pGd08b

Cloned from the equally unroutable pGd08a

Moved UART xtal next to the bottom of UART

07:46 - 07:51 at 11 passes failed on 4
07:53 - 07:58 at 16 passes fialed on 4

Abandonned.

### Pro pGd08c

Cloned from the equally unroutable pGd08b

Moved C10 to bottom of U5 as a last ditch attempt to route

08:00 - 12 passes fail on 8 08:04

Abandonned

#### Pro pGd09

Cloned from pGd08

Moved UART XTAL back next to UART pins on lower left side (again), with caps and res

22:56 7 passes 87 via (22:59), #1 87->79, #2 79->70 (23:07), #3 70 (23:14), #4 67 (23:22), #5 67 (23:26), #6 67 (23:33), #7 67->66 (23:41), #8 66 (23:44), #9 66 (22:53), #10 66->65 (23:59), #11 65 (22:07) #12 65 (00:14), #13 65 (00:23) #15 65 (00:37),  end  65   (est. 58  = 12 vias less than end of #2).

TL: 8.180

An excellent start. good progression, faltered at the end though. Not bad though, considering the crystal in the bus lane

If this doesn't route, move the UART cap back up as it is in pGd07


#### Pro pGd09a

Cloned from pGd09

Silkscreen errors fixed.

Really this should still be 09 as no components moved.


#### pGd10


Cloned from pGd09

move up HL3 and HL4 and U6 and u8 one notch to give room for bus label silkscreen


08:39 failed on 6 at #20

Shifted up U6 and U8 caps in vain hope

10:33 #9 failed on 8 traces

Abandonning???

Moved up one notch R9 closer (why wan't it before?)
Moved UART cap C11 down a notch


10:42 14 passes failed on 2 10:50

Moved and rotated R7 closer to UART

10:51  #8 failed on 4

Moved R4 next to U8 pin

10:58 failed on 4 (11:04)

Move C10 to U5, and C9 closer to Z80

18:28 #9 failed on 7 (18:33)
18:34 #9 failed on 7 (18:38)


Moved up switches

18:41 weird fail on ripping at #34

Moved resistor next to /WAIT on CPU

18:48 #11 failed on 6

Abandonned!!! Utter waste of time

Shifted U6 and U8 (an the other three things) to the right

01:49 failed on 3
01:56
12:41 failed on 2

Seemingly unroutable

Note: It is probably time to call it quits on this project. Stick with the 63 vias!

#### pGd10a


Cloned from pGd10a

Move U7 and cap and crystal and caps to the right

12:47 #9 failed on 7 #14 failed on 5, #21 failed on 2

Pointless!


#### pGd11

Cloned from pGd10

Manually routing

<!-- Images -->

  [6]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_1.png "Z80 Playground v1.2 - PCB front#1"
  [7]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_2.png "Z80 Playground v1.2 - PCB front#2"
  [8]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_3.png "Z80 Playground v1.2 - PCB front#3"
  [9]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20rear_1.png "Z80 Playground v1.2 - PCB rear#1"

