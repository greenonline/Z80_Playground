# Z80 Playground v1.2 - routing

## Preamble

The Z80 Playground v1.2 routing, as derived from the images shown in the video, [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them](https://www.youtube.com/watch?v=MaolTlk7XKM).

In retrospective, this wasn't overly difficult, just time consumming. Although I had two major hurdles: forgetting to place the mounting holes before finialising routing, and; the orientation of the TTL serial connector.

The first issue was solved by some manual re-routing. The same for the TTL serial connector. However, in the latter case, the orientation of the TTL serial connector in original layout by John Squires suited *his FTDI module*, as shown in [Flow Control for UART Serial communication between Z80 Playground and a PC](https://www.youtube.com/watch?v=RFxSKGnuisE) at [8:56](https://www.youtube.com/watch?v=RFxSKGnuisE), which has less common *reversed ordering* of the connectors. So, most fortuitously, it transpired that *my* original orientation of the connector was suitable for the more usual clone red FTDI module.

In addition, placement of the crystals required numerous iterations, and re-routing, although these were mostly down to poor initial placement decisions, and then further indecision.


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

For RCBUS40, the routing took about 30 minutes, and then another 30 minutes optimising to get from 88 to 72 vias, over 9 passes.

For the more "busy" RCBUS80 it took about the same amout of time. But the first attempt got up to 10 passes and then another 42 passes with 2 failed to route and it seemed stuck. The second attempt successed on around ten passes in around ten minutes. Then optimised for 10 passes to reduce the 101 vias down to 91 vias, after one pass. Down to 90 after two passes, and 89 after 3 passes. 87 after 6 passes. 86 after 7.

For the GOL:

 - routing; 10, 10 min
 - vias 88

For the Squires: (first attempt seemed stuck at 11 passes with 8 fails, secornd attempt #11 6 fails)

  - routing: 11, 15 min
  - vias:  87

You can save the freerouting seesion and then continue optimising or whatever, if you wish. However, you have to export a Specctra Session, from Freerouting, if you wish to import it back into the PCB Editor of KiCAD.

Unfortunately, you can not optimise a layout after reloading back into freerouting for further post-routing processing, which is a shame.

The PCB layouts, subsequent to autorouting, turned out to have many DRC issues (overlaps), which was annoying – a waste of three hours! - meaning that the boards needed redoing. There was also an issue relating to different rules(?) used by freeroute and KiCAD, as KiCAD completed that vias were too close to eachother and to tracks. Maybe KiCAD's rules are out-of-date? There is a `.rules` file, which I assume freerouting produced (as it does ask to save those as well, when saving the Specctra session), so maybe these need to be loaded into KiCAD inorder to prevent the DRC errors?

RCBUS80/40, with a new connector and no DRC overlaps:

  - routing: 9, 10 min
  - vias:  92 down to 92, apparently no optimisation possible? But D4 on edge connector not connected, the only DRC error.

RCBUS80/40 Attempt 2, with a new connector and no DRC overlaps:

  - routing: 
  - vias:  DID NOT ROUTE

RCBUS40, with no overlapping U2 and U11

  - routing: stuck on 2
  - vias:  DID NOT ROUTE
 
GOL: Flipping H2 such that VCC is left most, not A15, makes the routing much easier??? In other words do not put H2 on rear side of boar to make A15 on the left! However, that is the Squires bus, and not the RC2014 bus – The Squires bus is deliberately easy to place and route. 11 passes , 101 vias. 1st pass down to 88 or less, but noticed error in CH376S placement. Next attmepts: 10 or so, 85 vias, 1st pass down to 85 or less. Next: 

The decoupling capacitors are not autorouted to their ICs correctly – might need to manually do that first!

GOL: the cap on C10 and U5 needed swapping.

##### Further attempts

Note: Aiming for 65 vias, or less. RCBus variants seem more exacting, so a higher number of vias is expected. It may also depend upon the orientation of the RCBus connector – whether placed on the front or flipped on the rear of the board.

Strange that after repositioning overlapping component, autorouting would not complete:

 - RCBUS80 - 6 unrouted
 - RCBUS40 - 2 unrouted
 - RCBUS80/40 - 4 unrouted

I'm not sure what the issue was, but after some rearranging, and corrections, realignment, the boards successfully autorouted once more, and I let the optimiser run its coure in each case. Here are the results: 

 - SQUIRES - 14, 10 mins, 90 vias, #1 76, #2 73, #3 73, #4 70, #5 69, #6 69, #7 69, end 65
   - Squires - overlapping U1 and U5! and R? with U11. And CH375S was incorrect. Many corrections.
 - SQUIRES - #2 73, #3 69 vias, #4 69, #5 67, #6 67, #7 66, #8 66, #9 66, #10 66, #12 66, #13 66, end 66 (5hr?) - DRC PASSED!!!!!
   - DONE: SQUIRES2 (aligned): Could move up R8C1C2R15, but ok for moment
   - DONE: SQUIRES2v: Bad J5 -> J7 and J8, and bad alignment - easy manual fix?
 - GOL/MJ - ~15 route passes 10 minutes, 90 vias, #1 79, #2 73, #3 70, #4 67, #5 65, #7 64, #8 64, #8 63, #9 63, #10 63, #11 63, #12 63, #13 63, #14 63, #15 63, #16 62, #17 62, #18 62, #19 62, #20 61, #21 59, #22 59, #24 58, #25 57, #26 56, #27 56, #28 55, #29 54, #30 54, #31 53, #32 53, #33 51, #34 50, #35 50, #36 50, #37 50, #38 47, #39 47 (8 hours), #40 47, #41 47, end 47 (9hr) - DRC PASSED!!!
   - DONE: GOL2 (aligned): Could move R1R2 to the left, but ok for moment
   - DONE: GOL2 (aligned): Bad J5 -> J7 and J8, and bad alignment - easy manual fix?
 - RCBUS40 - ~15 route passes 10 minutes, 116 via, #1 102, #2 84, #3 83, #4 83, #5 83, #6 79, #7 78, #8 78, #9 77, #10 77, #11 77, end 77 (1hour, 1.5 hours) - DRC PASSED!!! But for the two header pin overlapping courtyard, as expected
 - RCBUS80/40 - 8 route passes (5 mins), 94 vias, #1 84, #2 79, #3 76, #4 76, #5 76, #6 74, #7 73, #8 70, #9 69, #10 69, #11 69, #12 69, #13 69, end 69 (1.5 hour) - DRC PASSED!!! But for the two header pin overlapping courtyard, as expected
 - RCBUS80r - 12:00 - 8 route passes (6 mins?), 94 vias, #1 85, #2 79, #3 76, #4 76, #5 76, #6 76, #7 74, #8 70, #9 ??, #10 69, #11 , #12 , #13 , end 69. 
   - Corrupted board, missing J5???
   - Corrupted, confusion .ses for rcbus80 was in rcbus80/40 directory - maybe I loaded the wrong .dsn from the wrong directory -> IGNORE THIS RESULT!
 - RCBUS80r - 8:55 - 10 route passes (7 mins?), 129 vias, #1 110, #2 103, #3 100, #4 100, #5 ??, #6 ??, #7 ??, #8 94, #9 94 (10:24), #10 94, #11 94, #12 94, #13 , #14 94, #15 94 end 94 (11:25).  - DRC passed!!! except for overlapping 
   - Do second attempt of RCBUS80r, to try to reduce the via count from 94.
 - RCBUS80r#2 - 11:30 -  route 10 passes (6 mins?), 129 vias, #1 110, #2 ??, #3 97, #4 97, #5 95, #6 ??, #7 93, #8 93, #9 93, #10 92, #11 92, #12 92, #13 88, #14 88 (13:30), #15  87, #16 87, #17 86, #18 85, #19 84, #20 84, #21 84, end 84. - DRC passed!!! except for overlapping

RCBUS reversed square pin of 40/80 pin header on left (denoted by r suffix)
RCBUS non-reversed square pin of 40/80 pin header on right

Current models, need renaming r/f - DONE!

 - RCBUS40f
 - RCBUS80r
 - RCBUS80/40r
 - RCBUSf

Re-route using inverse r/f

Both MJ/GOL and Squires are reversed

 - RCBUS80f - 14:49 -  route 50 passes (failing on 2) (10 mins?).
 - RCBUS80f#2 - 15:00 -  route 50 passes (failing on 2) (8 mins).

Maybe RCBUS(80) forward is harder (impossible?) to route?

 - Squiresr aligned: - 15:09 -  route 14 passes (5 mins), 100 vias, #1 86, #2 84, #3 79, #4 76, #5 76, #6 76, #7 76, #8 ??, #9 74, #10 ??, #11 73, #12 73, #13 ?, #14 72, #15 72 (2 hours),  end 72.
 - MJ/GOLr aligned: - 16:54 -  route 9 passes (5 mins), 83 vias, #1 73, #2 67, #3 63, #4 ?, #5 61, #6 60, #7 60, #8 60, #9 60, #10 60, #11 60, #12 60, #13 60, #14 60, #15 60, #16 60 (1.5 hr), #17 59, #18 59, #19 59, #20 59, #21 59, #22 55, #23 54, #24 53, #25 52 (20:15), #26 51 (20:35), #27 50, #28 50, #29 50, #30 49, #31 49, #32 48, #33 48 (22:30), #34 47, #35 47 (23:10), #36 47, #37 47, #38 47 (00:15), #39 47 (00:31), end 47 (00:48) (8 hours).

Creating RCBUS40r from RCBUS40f: got to 13 route passes and nothing, just ripping. Aborted.

Starting from blank slate:

 - RCBUS40r - 1:50 - route 8 passes (2 mins), 88 vias, #1 70, #2 65, #3 65, #4 62, #5 61, #6 60, #7 57 (2:20), #8 57, #9 57, end 57 (2:30).
 - RCBUS80f - 2:40 - nearly failed on 4. route ~15 passes (7 mins), 129 vias, #1 115, #2 106, #3 99 (03:30), #4 ?, #5 ?, #6 ?, #7 ?, #8 94, #9 ?, #10 93, #11 93, end 93 (04:32).

The Squires version of the schematic is a bit messy, which is mostly down to the use of lower case for some of the pins, tracks and (sheet) connectors. The GOL version uses homogenised upper case for all pins, tracks and (sheet) connectors.

Whilst the end result of vias is a good measure, in order to determine difficulty of routing you need to examine all of the data, including time and starting vias.

 - RCBUS80/40f - 04:38 (fails on 6 0447 6 0455) - shifted bus connector down to route. route ~14 passes (10 mins), 133 vias, #1 115, #2 108, #3 105 (05:30), #4 103, #5 101, #6 100, #7 100 (06:15), #8 99, #9 ?, #10 ?, #11 ?, end 95.

Minor fixes (J7 and J8 and J1 and J2) to Squiresr and (J7 and J8 and C8) GOLr – both aligned2.

GOLf derived from GOLr (aligned2) and flipped connector:

 - Normalisation of Net XTAL1 failed for GOLf when opening .dsn in freerouting? Didn't seem to make any difference when importing back into KiCAD - spurious error?
 - GOLf - 13:27 - (#14 failed on 2 13:30) Route 17 passes (3 mins), 105 vias, #1 103, #2 93, #3 84, #4 83, #5 82, #6 82, #7 82, #8 81, #9 81, #10 81, #11 80, #12 79, #13 79, #14 79, #15 79  end 79. (14:45)
 - SQUIRESr - aligned3 (Moved C8 and R16) - 15:00 - Route 11 passes (3 mins), 76 vias, #1 68, #2 62, #3 58, #4 58, #5 58, #6 58, #7 56, #8 56, #9 56, #10 56, #11 56 (15:45), #12 56, #13 56, #14 56, #15 56 (16:00), end 56 (16:09).

Squiresf derived from Squiresr (aligned3) and flipped connector:

 - Squiresf - aligned3 - 16:14 - Route 24 passes (6 mins), 96 vias, #1 81, #2 79, #3 76, #4 75, (16:35), #5 74, #6 74 (16:50), #7 74, #8 74, #9 73, #10 73 (17:08), #11 73, end 73 (17:15).

Squiresr/f - U11 slightly off board! - DONE! (aligned4)

 - Squiresr - aligned4 - 17:26 - Route 10 passes (3 mins), 82 vias, #1 80, #2 75, #3 64, #4 61, #5 61, #6 59, #7 59, #8 59 (18:00), #9 58, #10 58, end 58 (18:15).
 - Squiresf - aligned 4 - 18:22 - (failed on #80 2 18:27, #100 2 18:34, #140 2 18:42, #160 2 18:50 ) 18:52 (after shifting bus connector down ever so slightly (enough for an extra track or two?)) - Route 8 passes (3 mins),  84 vias, #1 84, #2 75, #3 73, #4 72, #5 71, #6 71, #7 70, #8 70, #9 70, #10 69 (19:31), #11 69,  end 69 (19:43).

### Routing log

After the initial and further routing attempts, I more or less had a base line from which to work from, and a better idea of what to expect regarding results.

Here follows an unabridged log of all routing attempts and board changes.

#### Re-runs of Squiresr

To get that elusive 56 vias of "align3", before the off-board IC was moved:

 - Squiresr - aligned4 rerun - 20:06 - Route 10 passes (3 mins) - 83 vias, #1 80 (79?), #2 79->71, #3 70, #4 67, #5 65, #6 63, #7 63, #8 63, end 63 (discarded).
 - Squiresr - aligned4 rerun - 20:54 - Route 10 passes (3 mins) - 83 vias, #1 78, #2 78->71, #3 71->71, #4 71->70, #5 70->67, #6 65, #7 65, #8 65, #9 65, #10 65, end 65 (discarded).

Maybe lower Squiresr bus connector a row or two, right up to the edge, in order to reduce via.  Although it seems to be the same as align3. Left unchanged.

Note that align4a is cloned from align4.


 - Squiresr - align4a rerun - 22:38 - Route  passes ( mins), 193 vias (Aborted), #1, end.
 - Squiresr - align4a rerun - 22:45 - Route  passes ( mins), 83 vias (Aborted), #1, end.
 - Squiresr - align4a rerun - 23:05 - Route 10 passes (4 mins), 83 vias (Aborted), #1, end.


Shifted bus down to edge:

 - Squiresr - align4a rerun - 23:36 - Route 10 passes (4 mins), 84 vias (Aborted), #1 76, #2 72, #3 69, #4 69, #5 64, #6 64, #7 61, #8 57 (00:28), #9 56, #10 56, #11 55 (00:40), #12 55, #13 55, #14 54, #15 54, #16 54, #17 54, #18 54, #19 54, end 54 (01:18).

Superlative result, easily beating the best align4 result so far, 58, by 4 fewer vias. Plus, not only equaling but also exceeding even align3 by 2 fewer vias! Moving the bus connector down to the edge certainly did the trick!

Short trace too (i.e. less than 8,000,000 µm): 7,899,734.31 µm -> (#17->#18) -> 7,900,283.11 : 7,899,929.78

Improvemnts Squires, and maybe also GOL (Also check RCBUS variants): 

 - Maybe move RAM up and its cap to the left side, instead of on top
 - Maybe move ROM right and its cap to the left side, instead of on top - No, not in original
 - Maybe move UART/C8/R16/etc. right and its cap to the left side, instead of on top
 - Put C10 closer to U5
 - Move serial port down? Dimensions of serial board?

#### Reruns RCBUS80r

Aim: to reduce below 84 vias. Historically high via count at start (>120):

 - RCBUS80r - 03:23 - Route ? passes (? mins), ?? vias, #1, end 94. Discarded
 - RCBUS80r - 11:45 - Route ? passes (? mins), 128 vias, #1 108, #2 107, #3 100, #4 95, #5 94, #6 94, #7 94, #8 94, #9 94, #10 94 (13:24), #11 94, #12 94 (13:41), #13 94, #14 94, (13:51), #15 94 (14:11), end 94 (14:20). Ultimately discarded.

#### Improvements to RCBUS(80r) layout: RCBUS80r3

Improvements to RCBUS80r -> RCBUS80r3 (check all RCBUS variants, these changes probably also apply.)

 - Put C10 closer to U5 and on top instead of to the side
 - Put C7 closer to U7 (move silkscreen), C7 in line with LEDs
 - Swap orientation of C3 and put right next to U3 (move silkscreen)
 - Move up switches? No, left as is
 - Orientation of C5 and C6? OK, left as is
 - Move C12 closer to RAM
 - Silkscreen fixes (orientation, position, offboard markings fixed, R8C1C2R15 silkscreen tidied)
 - Moved together R8C1C2R15, once the silkscreen marking were moved. Nice and close now.

Routing:

 - RCBUS80r3 - 14:21 - Route 12 passes (7 mins), 120 vias, #1 105, #2 100->91, #3 90 (15:00), #4 90, #5 87->84, #6 84, #7 84 (15:30), #8 83, #9 83 (15:45), #10 83, #11 83, #12 83 (16:05), #13 83, #14 83 (16:15), #15 83, end 83 (16:29).

Interesting, one less via than RCBUS80r – not a bad result.


#### Mounting holes: RCBUS80r2

RCBUS80r2 is cloned from RCBUS80r and holes added.

> To add holes in KiCad 6, use the Add Footprint tool in the PCB editor to place a Mounting_Hole footprint, or draw a circle on the Edge.Cuts layer if you need a custom non-plated cutout hole. The former provides for DRC checks, the latter more (unchecked) freedom.

M2 for least disruption. REF1 top left, then numbered clockwise (REF2, REF3, and REF4). Placed on extreme edges/corners, in a hopefully slightly rectangular pattern – vertical is slightly shorter, owing to the bus connector, than the horizontal.

Holes have REF and footprint description set to not visible. Grouped as 4, for easy copy and paste, between boards, in order to maintain consistancy.

Had to shift capacitors down for the top right hole, but that is the only component shifted – apart from the bottom right traces over-written/drilled-through).

Footprint: `MountingHole_2.2mm_M2_DIN965_Pad`

RCBUS80r2 has mounting holes added. How will it affect the routing from 84/94 vias? Will it make it hrder, i.e. even more vias? Proabably, but this is a needless test as r5 is more interesting. Note that RCBUS80r2 does not have the RCBUS80r3 enhancements above.

Just trying to fix the changed/broken/overwritten traces from RCBUS80r:

 - RCBUS80r2 - 16:30 (fails on #24 3 aborted) - Route  passes ( mins),  vias, #1, end. 

Retrospectively, not a great loss as the starting point would have been 84 vias, anyway.

Starting from a blank slate is better, as the results clearly show:

 - RCBUS80r2a - 16:32 - Route 18 passes (5 mins), 102 vias, #1 92, #2 82, #3 81 (17:03), #4 81 (17:15), #5 81, #6 81, #7 80, #8 79 (17:44), #9 79 (17:51), #10 79, #11 79, end 79 (18:13). 

A rather surprising result, 79 is not only less than the 94, but also lower than the 84 vias of RCBUS80r, and even less than the 83 of RCBUS80r3 as well..!

#### Combined: RCBUS80r5

r2+r3 = r5 (shifted the XTLs down):

 - RCBUS80r5 - 18:14 - Route 9 passes (5 mins), 109 vias, #1 97, #2 92, #3 90, #4 89 (18:46), #5 89, #6 89, #7 88 (19:17), #8 87, #9 87, #10 87, #11 87, #12 86 (19:48), #13 86 (19:57), #14 86, #15 86, #16 86 (20:19), #17 86, #18 86 (20:34), #19 86 (20:44), end 86 (20:48). 

High trace length?

At least 86 vias is less than the 94 of RCBUS80r and, although not quite as low as 84, it is still a respectable figure. Not as low as 79 vias of RCBUS80r2a though. Re-run, as RCBUS80r5a:

 - RCBUS80r5a - 21:10 - Route 9 passes (5 mins), 109 vias, #1 97, #2 92, #3 92->90?, #4 90?->89 (21:45), #5 89, <PAUSED>, end ??.

Seems to be an identical run. Paused and saved, see if able to continue later.

Should move C5 and C6 and C17 and C18 closer to XTALs. RCBUS80r6?  


RCBUS5b: Shift U5 to the right and up. Shift UART up, followed by ROM, CPU. Not moved XTAL caps.

 - RCBUS80r5b - 21:59 (failed on #30 3 22:07, failed on #30 3 22:14) - Route  passes ( mins),  vias, #1, end.

Seems unroutable!

RCBUS80r5c: As per RCBUS5b but then shift U5 back to left (but not back down)

 - RCBU80r5c - 22:17 - Route 8 passes (4 mins), 97 vias, #1 86, #2 79, #3 75, #4 74, #5 74, #6 74 (22:51), #7 74, #8 72, #9 72, #10 72, #11 72, #12 72, #13 72 (23:26), end 72 (22:34).

Lower trace length than RCBUS80r5 as well, although still over 8M.

Much better! Superlative even! First optimisation pass already equals RCBUS80r5 (86). Second optimisation already equals RCBUS80r2a (79). Sets a new gold standard of 72, which is good, especially considering that the RCBus80 is the most complex bus. 

Shifting up really helped. Leaving a gap by the right edge of the board of U5 also helped.

C1 and C2 are not level! - DONE! Fixed manually.

Could move buttons up? A little bit.

Should maybe just concentrate on RCBU80r/f as the others can just have different connectors attached. Yes, RCBUS40r/f might be easier to route, but who cares all that much about how many vias? It is only 15 vias anyway!

#### RCBUS80f <- RCBUS80r5c layout: RCBUS80f2

Now RCBUS80f2, pasting in the superlative component layout of RCBUS80r5c (apart from the bus connector), with 93 vias (of RCBUS80f) to beat:

 - RCBUS80f2 - 23:47 - Route 14 passes (9 mins), 132 vias, #1 116, #2 105, #3 103 (101?), #4 101->99, #5 99->97, #6 97->95, #7 95, #8 95 (01:10), #9 95 (01:20), #10 95 (01:30), #11 95 (01:40), #12 95 (01:48)-> 94 (01:52), #13 94 (01:58), #14 94 (02:07), #15 94 (02:14), #16 94 (02:23), #17 94 (02:32), #18 94 (02:42), #20 94 (03:00), end 94 (03:10).

Very high trace length 8.7M! -> 8.62M

C1 and C2 are not level! - DONE! Fixed manually

Starts one via higher than RCBUS80f (131, plus #1 115, #2 106, #3 99, ...). Clearly the forward orientation of the bus is more difficult to route. 

Not a stunning result, actually a regression by +2 vias.

Not a terrible regression, only +1 via.

The addition of the bottom right hole (REF3) has visibly caused a via to be required, in order to reach the bus connector. Not possible to shift the hole up?

If this isn't better than RCBUS80f (93) then just make RCBUS80f3 a clone of RCBUS80f, and paste in the holes and move XTALs (without shifting the ICs) and retry.

TODO: Change REF to HL.

#### RCBU80f3: Minimal hole addition

Clone of RCBUS80f. Literally just paste in the holes and move the top XTAL. 

 - RCBUS80f3 - 03:11 - Route 13 passes (8 mins), 135 vias, #1 120 (119?), #2 119->105 (03:30), #3 105->102 (03:43), #4 102->101 (03:57), #5 101->101 (04:08), #6 101 (04:17), #7 101 (04:30) end 101 (07.40).

Trace length: 8.77M

Starts four vias higher than RCBUS80f (131, plus #1 115, #2 106, #3 99). Clearly the forward orientation of the bus is more difficult to route. 

Is this result an outlier? 101 vias seems rather high.

 Re-run as RCBUS80f3a - 11:53 - Route 17 passes (13 mins), 130 vias, #1 130->115, #2 115-> 107 (12:19), #3 107->106 (12:31), #4 106 (12:46), #5 105 (12:53), #6 104 (13:02), #7 104->103, (13:12), #8 103 (13:24), #9 100->99 (13:37), #10 99 (13:42), #11 99 (13:54), #12 99 *13:58), end.

Trace length: 8.86M->

A bit better, better than 101 at least, but still worse than 93/94.

If this is not good, then try the RCBUS80r5c changes, but without the IC shift.

#### RCBU80f4: Much realignment, but no IC shift

Clone of RCBUS80f. Shifted just one (top) XTAL, moved D5,D6, R14, reoriented R14, moved C7. Also shifted C10 on top of U5. Nice little change. Did not change ICs - that is the major difference from RCBU80f2.

Leveled C1 and C2, and moved closer together, as per the RCBUS80r3 change.

 - RCBUS80f4 - (07:40) - Route ? passes (? mins), ? vias, #1 ?, #2 ?, #20 87 (11:33), #21 87 (11:44), end 87 (11:52).

High trace length: 8.98M

A surprisingly good result, reducing 93 -> 87, by 6 vias.

#### Exercise in futility - RCBUS80f

These variants of RCBUS80f, the forward, or front, orientation of the RC2014bus connector, really are a very time-consuming exercise in futility as they merely serve to show, through their high number of vias (87-98), that the reverse, or rear, orientation of the RC2014 bus is more viable, resulting in (far) fewer vias.

Just focus on the RCBUS80r, and reducing via count below, the superlative, 72. Maybe also the RCBUS40r variant, for connection to simple motherboards, reducing from 56. RCBUS80f is 77 vias, so could try four variants again, as per RCBUS80f.


#### Fixing up RCBUS80r5c: RCBUS80r6

Fixed C1 and C2 not level. Easy manual fix. Still the same as RCBUS80r5c – no PCB changes.


#### RCBUS40r2 with holes

Cloned from RCBUS40r
R8C1C2R15 close together
Plus C7, C10 adjustments
Only top crystal shifted down.
Bus connector shifted down
No IC shift.

57 vias to beat:

 - RCBUS40r2 - 14:34 - Route 7 passes (3 mins), 84 vias, #1 81->?, #2 76->72 (14:43), #3 70 (14:50), #4 68 (14:56), #5 67 (15:00), #6 67->66 (15:03), #7 65 (15:11), #8 65 (15:15), #9 65 (15:19), #10 65 (15:25), #11 65 (15:30), end 65 (15:38).

Trace length: 7.92M

Certainly nothing to celebrate! 65 is far from 57.

Orientation of C3, C10 needs swapping

### RCBUS40r3 with holes

Cloned from RCBUS40r
Only top crystal shifted down.
Not blank slate.

Manually re-routed, maintaining 57 vias of RCBUS40r.

This is a CANDIDATE... although it could do with C3, C10, C12 swapping

### RCBUS40r2a with holes

Cloned from RCBUS40r2
Orientation of C3, C10, C12 swapped
Other silkscreen fixes.
Quite a good little placement.
Blank slate.

 - RCBUS40r2a - 15:40 - Route 7 passes (3 mins), 84 vias, #1 72->??, #2 ??->71->64->?? (15:48), #3 63->62 (15:55), #4 62 (15:59), #5 61 (16:03), #6 61 (16:07), #7 61 (16:12), #8 61->59 (16:15), #9 59 (16:19), #10 59 (16:23), end 59 (16:30).

Trace length: 8.12M -> 8.05M -> 7.99M

Very similar to the original RCBUS40r routing run.

A Candidate: Good component layout, low trace length, lowish via count, although not as low as RCBUS40r3 (57).

#### RCBUS40r3a

Clone of RCBUS40r3

Slow component by component realignment: RCBU40r3a, RCBU40r3b, RCBU40r3c, ..., etc.

Just changing R8C1C2R14 added 3 vias to 60, when autorouting just that bit, not blank slate

Blank slate:

 - RCBU40r3a - 17:05 - Route 11 passes (3 min), 77 vias, #1 74, #2 70->62, #3 62->61, #4 ??, #5 57 (17:20), #6 57 (17:36), #7 56, #8 56->55 (17:46), #9 55 (17:51), #10 55 (17:54), #11 55 (17:58), end 55 (18:14).

Track length: 8.01M

Very good result, no regression and actually an improvement by -2 vias. A new gold standard of 55 vias!

C3, C7, C10 and C12 need doing. Although C10 could be left as it is. C3 should be an easy manual change. C7 should be easy. C12 could be a problem.

#### RCBUS40r3b

Clone of RCBUS40r3a
C3 was an easy manual change.

#### RCBUS40r3c

Clone of RCBUS40r3b
C7 was an easy manual change.
Silkscreen also fixed.

Just the RAM capacitor, C12, to fix really. To be fair, it might not be essential.

#### RCBUS40r3d

Clone of RCBUS40r3c
C12 was not an easy manual change.
Auto routing just the change/move failed. Trying new slate, although unlikely to beat 55 vias:

 - RCBUS40r3d - 18:33 - Route 10 passes (4 mins), 77 vias, #1 77->74,  #2 73->68 (18:43), #3 63 (18:48), #4 63->62 (18:52), #5 61 (18:57), #6 61->60 (19:02), #7 59 (19:07), #8 56 (19:12),  #9 56 (19:14), end 56 (19:21).

Track length: 8.07M

Real shame about the regression by +1 via.

#### RCBUS40r3e

Rerun of RCBUS40r3d, clean slate

 - RCBUS40r3e - 1941 - Route 9 passed (3 mins), 79 vias, #1 77, #2 69, #3 65, #4 65, #6 65, #7 65, #8 65, (accidentally stopped and restarted) #1 65, #2 61, #3 61, #4 61->59, #5 59 (20:35), #6 59->58 (20:38), #7 58 (20:42), end 58 (20:45).

Track length: 7.84M

Even worse than RCBUS40r3d! Regression +3.

#### RCBUS40r3f

Clone of RCBUS40r3d/e

Move C12 slightly to the left

 - RCBUS40r3f - 20:47 - Route 7 passed (3 mins), 76 vias, #1 76->71, #2 71->64 (20:56), #3 64->64 (21:02), #4 64->60, #5 60->57 (21:12), #6 57->55 (21:16), #7 54 (21:21), #8 54 (21:25), #9 54 (21:30), #10 54 (21:36), #11 53 (21:41), #12 53 (21:44), #13 53 (21:49), #14 53 (21:53),  #15 53 (21:57), #16 53 (22:02), #17 53 (22:06), end 53 (22:18).

Track length: 8.14M -> 8.02M

Promising start. Superlative result.


### New worries (bypass and crystal caps)

 - While the VCC is closely connected, the GND is not.
   - However, as it doesn't have to be the same cap, then so long as the ICs' GNDs are connected to another cap (pertaining to some other IC) then it doesn't matter!
     - TODO: Check this!
   - To fix missing ground connections vias will need to be added.
   - Add GND plane?
   - Add VCC plane?
   - Use two caps, one for VCC and one for GND? Maybe just for CPU, ROM, UART and RAM?
     - This would be the most professional/secure option, whilst maintaining through-hole components (not resorting to SMD)
     - [How to connect decoupling capacitor when VCC/GND pins aren't close ](https://electronics.stackexchange.com/questions/9888/how-to-connect-decoupling-capacitor-when-vcc-gnd-pins-arent-close)
   - Place near the the GND pin, and not the VCC?
     - [maximum distance between IC power pins and decoupling capacitor](https://electronics.stackexchange.com/questions/275213/maximum-distance-between-ic-power-pins-and-decoupling-capacitor)
   - Just bodge some additional caps in afterwards on the back-side of the PCB or in/under sockets..?
     - And leave the PCB caps unpopulated
     - And mark the PCB caps as unplaced?
     - Remove from schematic?
       - Can mark as "not placed"?
     - Just make the boards as is (maybe try to fix with one via or two). Then add underside caps if not working, or as needed. 
       - This is the simplest option, but messy -> unnedded caps.
       - Cover in captan tape? 
       - Heatshrink on each leg. 
       - Heatshrink covering whole length of capacitor, for extra protection?
   - Just bodge on some wire to the GND (and VCC) terminals of the nearest decoupling cap
   - Use SMD on underside, or front?
 - Move the caps closer to the top xtal. Swap with R14


#### RCBUS40r3f-> RCBUS40r3g:

To fix missing ground connections vias will need to be added.

Fixing bypass grounds, as the VCC connections are all fine, due to the proximity:

 - UART GND bad
 - ROM GND bad
 - RAM OK
 - CPU GND bad
 - U5 OK
 - U6 fixed added one via.
 - U8 fixed added one via
 - U7 50-50

Vias = 55



#### RCBUS80r5d

In an attempt to reduce the vias on RCBUS80.

Cloned from RCBUS80r5c

C10 put back to the right side of U5, on a whim, just to see what happens (72 vias is the target):

 - RCBUS80r5d - 23:35 - Route 17 passes (6 mins), 134 vias, #1 134->126->127!->125, #2 ??->113->108 (23:57), end. ABORTED

Not a promising start. The horizontal from the GND of C10 to U5 doesn't seem to be doing anyone any favours. Aborted.


 - RCBUS80r5d - 00:00 - Route ~10 passes (4 mins), 114 vias, #1 114->105, #2 102->93 (00:20), #3 93->90 (00:28), #4 88->86 (00:37), #5 ?, #6 85->82, #7 82->82 (00:53), #8 82 (01:01), #9 82 (01:07), #10 82 (01:15), #11 82 (01:19), #12 82->73 (01:27), #13 73->>71 (01:49), #14 71->68 (02:11), #15 68->64 (02:27), #16 64->64 (02:43), #17 64 (02:56), #18 64->61 (03:15), #19 61 (03:26), #20 61 (03:49), #21 60 (04:10), #22 60 (04:23),  end 59 (08:07).

Track length: 7.99M -> 7.95M

These passes take 15 minutes, longer than the previous 5 minutes or so.

The time may be slow to update when context task switching on the Mac - or it might just be coinsidence


A bit better start, although I think that it will be hard to top 72 vias. Amazing result!Can discard the need for the RCBUS80/40r (69 vias) – unless I am willing to do more test runs (and add holes) to/for RCBUS80/40r, in order to try to reduce vias below 69, but is there really any point? How popular is the RCBUS80/40r variant actually be? Better to put energy into RCBUS80r to reduce even further below 68/59?

Could almost dispense with RCBUS40r (53/55 vias) as well!

Move C10 to bottom left of U5, so close to the GND, instead of VCC? RCBUS80r5e

#### RCBUS80r5e

Cloned RCBUS80r5d

Moved C10 to bottom left of U5, so close to the GND, instead of VCC.

 - RCBUS80r5e - 0807 - Route13  passes (6 mins),122 vias, #1 122, #2 ?, #3 86, #4 ? #5 85, #6 84, #7 82, #8 82, #9 82, #10 82, #11 ? , #12 81->79, #13 79, #14 79, #16 79, #17 79->76, #18 74->69 (10:43), #26 56 (13:55), #27 56 (13:59), #28 56 (14:17), #29 56 (14:32). end 56 (15;00)

High trace lengths : 8.13M

Amazing, incredible.

#### Extra planes: RCBUS80r5cp

Cloned RCBUS80r5c
Added VCC and GND plane, might help with decoupling caps?

 - RCBUS80r5cp - 15:16 (failed on #15 2 tracks, #28/2) - Routes <10? passes (3 mins), 83 vias, #1 83->79, #2 69->66 (15:30), #3 61 (15:40), #4 61->57 (15:41), #5 57->55 (15:48) , #6 55 16:00, #7 54 (16:04), #8 54 (16:12), #9 54 (16:16), #10 54 (16:25), #11 54 (16:32), #13 53 (16:43), #14 53 (16:47), #15 53 (16:56), #16 53 (16:59), #17 52->48 (17:05), #18 48 ->41 (17:22), #20 29 (17:55), #21 28->27 (18:05), #22 25 (18:18), #23 25 (18:32), #24 25 (18:43), #25 24 (18:53), end 24 (19:11).

Low trace length: 6.9M -> 6.73M

Initially did not want to route! Strange! Repeatedly (twice) failed on 2 traces. 

Interesting result, interesting new base line. At least the PCB is starting to look like a PCB now.

Also, probably better to clone RCBUS80r5e... or, looking a this result, maybe no need..!

Check how bypass caps are routed on 4 layer board.

Cons:

 - Many are not connected to VCC
 - Many planes not connected
 - C9 incorrect orientation!!! Check others. No it isnt you fucking idoit
 - Bollox to it, lost interest.

Pro

 - Much lower via number and cleaner routing.

### RCBUS80rPRO

Add extra/double the capacitors to schematic, one next to VCC pins and one next to GND pins, for a test, and do a run. This is the best option. The autorouter should auto-connect the closer capacitor terminals.

This might require four planes (additonal VCC and GND planes) as otherwise the need for additional VCC tracks (for the other end of the GND capacitor) will require more vias?

 - Pro has 4 layers?

The clocks should be next, or closer, to CPU and UART?

 - [Why should the crystal oscillator not be placed at the edge of the PCB?
](https://www.onzuu.com/blog/why-should-the-crystal-oscillator-not-be-placed-at-the-edge-of-the-pcb)
 - [Crystal And Capacitor Placement (I Should Have Read The Wiki)](https://www.reddit.com/r/PrintedCircuitBoard/comments/12p2220/crystal_and_capacitor_placement_i_should_have/)
Move all capacitors to next to GND.

 - RCBUS80rPRO - time - Route  passes (mins) - vias, #1, end.


Should the VCC and GND planes be internal?

Need a test of the 4 planes to see now the routing goes -> RCBUS80r5cp2

Properly renumber components

#### RCBUS40r3h

Cloned RCBUS40r3g
Added extra hole, below CH376S

#### RCBUS80r5cp2

Added GND and VCC to U8, U6, U7 and U5 and UART, ROM, RAM, CPU.
Tidied silkscreen warning for H2
The edge cut needs to be made huge, all encompassing, and then that gives 0 warnings.
Fixed all unconnected nets and planes

CPU added VCC to bypass (by 1 additional via)
Hid the silkscreen of the connector! Switched footprint to Connector_PinHeader_2.54mm:PinHeader_2x40_P2.54mm_Vertical, reduces most warnings.
TODO: Add holes to schematic? Can not do via "Update schematic from PCB"
Moved H2 silkscreen
Moved and changed CH376S connector silkscreen

Gerbers made


#### RCBUS80r5cp2a

Cloned RCBUS80r5cp2
Swapped C5, C6 with R14

TODO: Make this!!! 
Not needed as caps/xtals fixed in RCBUS80r5cp4

#### Finalise RCBUS80r5e

Remove all errors and warnings
Produce Gerbers
Compare the cost 

Hide the silkscreen of the connector! Switch footprint to Connector_PinHeader_2.54mm:PinHeader_2x40_P2.54mm_Vertical
Add holes to schematic?
Moved H2 silkscreen
Moved and changed CH376S connector silkscreen

 - 56 vias
 - Err/Warn: 1/6

Gerbers made

#### Finalise RCBUS40r3h

 - 55 vias
 - Err/Warn: 1/4

Gerbers made


#### Finalise Squiresr - aligned4a

 - 54 vias
 - Err/Warn: 1/18

Set H1 to vertical footprint

 - Err/Warn: 1/0

Gerbers made

TODO: Missing holes
TODO: R8C1C2R15 not aligned or close

#### Finalise MJ/GOLr - aligned2

 - 47 vias
 - Err/warn: 1/23

Set H1 to vertical footprint

 - Err/Warn: 1/2

Gerbers made

TODO: Missing holes
TODO: R8C1C2R15 not aligned or close
-> align3


#### Costs: 2 vs 4 layers

For RCBUS80r5e
2 layer: $2
For RCBUS80r5cp2
4 layer: $7


#### GOL align2p

Cloned from align2
4 planes

Added missing holes!
Shifted C5 U10 up
XTAL left (not down)
Shifted C4 up

 - GOL align2p - 19:27 - Route 8 passes (3 mins), 58 vias, #1 58->51, end. ABORTED


Trace length: 6.8M 

Aborted as noticed R8C1C2R15 not aligned or close (same for Squires)


 - GOL align2p -  19:44 - Route  passes ( mins),  vias, #1 , end. ABORTED

19:38 Failed on #21 4 or 5
19:44 Failed on 4 or 5

Moved C5 below U10

 - GOL align2p -  20:14 - Route 10 passes (4 min), 50 via, #1 50->44, #2 44-> (20:23), #3 44->41 (20:26), #4 41->39, #5 39->36 (20:35), #6 34->33 (20:40), #7 31 (20:44), #8 31->30 (20:47), #9 30 (20:51), #10 30, end 30 21:04. CORRUPTED!

Trace length: 6.72M

Also getting can't normalise XTAL net when opening .dsn in freerouting.

 21:07 - Route 10 passes, 50 via, #1,  - aborted (due to corruption and same as last result).

Fixed hole HL5 issue but still getting can't normalise XTAL net when opening .dsn in freerouting:

Failed on #

 - GOL align2p - 18:05 - Route ~13 pases (4 mins), 51 via, #1 51, #2 51, end 51 (18:10).

TL: 6.74M

Not an amazing start. Totally rubbish result. It didn't even bother trying to optimise its own work!

Cloned align2p

 - GOL align2pb - 18:14 - Route 8 pases (3 mins), 54 via, #1 54->47, #2 47->42, #3 41->40 (18:27) #4 38, #5 38, #6 37, #7 37, #8 37 (18:50), end 37 (19:00).

TL: 6.69M

A better run, although I would have expected a result similar to ~20 vias like RCBUS80r5cp.

Cloned align2pb. Made sure to clear routes in freerouting, re-import empty PCB back into KiCAD, refill middle layers and export again, and then route.

 - GOL align2pc - 19:07 - Route 8 pases (4 mins), 54 via, #1 54->47, #2 44, #5 38, #6 38 (19:35), #7 38, #8 38 (19:41), #9 38 (19:45), #10 36->32, #11 32->30 (19:58), #12 30->28 (20:06), #13 28 (20:15), #14 28->25 (20:24), #15 25->23 (20:31), #16 23->22 (20:38), #17 22 (20:47), #18 22 (20:54), #19 22->21 (21:03), #20 21, #21 21 (21:25), #22 21 (21:35), end 21 (21:41).

TL: 6.715M -> 6.78M -> 6.83M

An even better run, and it got much better at the end. I wouldn't be sure if 33 vias (over 47 or 48) is a good enough reason to move to 4 layer boards, but 24 or less (half of 48) probably is a good enough reason.

TODO: Finish off board DRC: align2pc2

Cloned align2pc

 - GOL align2pd - time - Route  passes ( mins), via, #1, end.

Deferred (as previous result was very good): Need to re-run RCBUS80rp to see if can get less vias: RCBUS80r5cp3 (clear in freerouting first)

Cloned align2pd

Moved C10 above U5 again, just to get a different result.

 - GOL align2pe - time - Route  pases ( mins), via, #1, end.

Deferred (as previous result was very good)

#### GOL align2pc2

Cloned GOL align2pc
Fixed DRC, unconnected islands.

DONE: Finish DRC checks
Crystals moved perfect
TODO: Need to fix the edge connector, shift up one notch: GOL align2pc3? A via has been used instead, from VCC Z80 to U5 VCC: 21+1 = 22 vias

TODO CPU VCC/GND to cap.

Err/Warn: 1/2

CANDIDATE

#### GOL aligned3

Cloned from aligned2
Missing holes added 
R8C1C2R15 not aligned or close
C5 above U10


 - GOL aligned3 - 20:08 - Route 9 passes ( mins), vias, #1, end.

21 failed on 2

Bad hole 5 fixed, pasted in new group from GOL aligned2b. But still the normalisation error when opening in freestyling – hopefully a spurious error, and not related to the missing image HL5 issue!?? Yes, seemingly a spurious error.

Noticed that R8C1C2R15 are now aligned and close, I must have tidied that up at some point and then forgotten.

 - GOL aligned3 - 13:03 - Route 11 passes (4 mins), 89 vias, #1 89->80, #2 76, #3 72, #4 72->71, #5 71, #6 71, #9 71, #10 71 (14:02), #11 71, #12 71, #13 71->70 (14:20), #14 70->68 (14:25), #15 68->67 (14:32), #16 67->65 (14:38), #17 65, #18 65->64 (14:55), #19 64 (14:57), #20 64->63, #21 63, #22 63 (15:11), #23 63 (15:20), end 63 (15:22).

TL: 8.13M

Err/Warn: 1/2

Try with C5 below U10: GOL aligned3a

#### GOL aligned3a

Cloned from aligned3

C5 below U10

 - GOL aligned3a - 15:22 - Failed #80 on 2, 15:28 #27 failed on 3, 15:34 #60 failed on 2 - Route  passes ( mins), vias, #1, end. Aborted.

Shifted C10 up two notches, right close to U10:

 - GOL aligned3a - 15:42 - Failed  on 2  15:49 failed #70 on 4, - Route  passes ( mins), vias, #1, end.

Impossible to route!

Rotated C5

 - GOL aligned3a - 15:55 failed on 2, - Route  passes ( mins), vias, #1, end.

Shifted up two notches C5 and U10

 - GOL aligned3a - 16:04 - Route ~10 passes (4 mins), 87 vias, #1 87->82, #2 80->67, #3 66 ->64 (16:29), #4 64->63, #5 61 (16:45), #6 60, #7 60, #8 60, #9 60 (17:08), #10 60 (17:18), #11 60, #12 60, #13 60 (17:42), #14 60, end 60 (17:58)	.

TL:8.06M

This is all academic and impossible to route. You'll never beat 47 vias for 2 layer. Better to concentrate on 4 layer. 

For 2 layer: 48 vias: GOL alignedb – with the HL5: GOL alignedc

Abandonned!!! Or not!

#### GOL alignedc

Cloned from alignedb
Added fixed HL5 holes group from aligned2pc2
Moved XTALs perfect.
R8C1C2R14 moved very close
CANDIDATE:


#### Squires aligned5

Cloned from aligned4a
Missing holes added 
R8C1C2R15 not aligned or close
Total mess!


#### Squires aligned4b

Cloned from aligned4a
Just add holes
Manually fixing. 
C10 and U5 shifted up
C13 shifted right
Mostly fixed but HL5 is the biggest problem as the UART needs to move: aligned4b2

R8 moved close to C1
C2 moved clsoe to R15
But C1 and C2 have not moved - yet, there are vias in the way, and it might be enoug space anyway, depending upon the location of the CH376S connector.

#### Squires aligned4b2

Cloned from aligned4b
Shifting UART and C3 down manually
Err/warn: 1/0
Perfect! (Except maybe for C1 and C2)

Edge connector could be shifted up (also on aligned4b2p)? Nah, no worries. It could be shifted , but it is ok, only silkscreen off board

C11 is the wrong way around! Fix: Squires aligned4b4

#### Squires aligned4b3

Just for fun/curiosity
Cloned from Squires aligned4b2
Shifted up bus connector one notch

 - Squires aligned4b3 - 21:23 (Failed on #19 2 traces) - 21:27 (failed on 2) - 21:33 -  passes, ( mins),  vias, #1 , end.

Will not route (3 fails). Abandonned.

#### Squires aligned4b4

Fixed C11 and some other issues (many silkscreen isues (xtals and caps, resistor markings vertical, LEDs), shifted LED reistors, plus a route and via under U3). 
Perfect.

Err/Warn: 1/0

 - Bus connector could be moved up a little, for better routing, the edge connector is properly on the board, just the courtyard isn't
 - R8C1 and C2R14 could be closer, but there are vias in the way, and maybe the space is ok, depending on CH376S connector placement.


-----

ALL GOL aligned >=2 are corrupted!!!!!!! Fixed now???


#### GOL aligned 2 

GOL aligned 2 is new
Cloned from aligned.
Holes added
C10 below U5
Many layout shifts for the holes.


 - GOL aligned2 - 21:56 - Route 10 passes (3 mins), 88 vias, #1 88, end (Aborted: bad C5/C6 rotated)
 - GOL aligned2 - 22:01 - Route 8 passes (3 mins), 97 vias, #1 97->89, #2 88->83, #3 81->74, #5 70, #6 69, #7 68, #8 68, #9 68, #10 68,#11 68, #12 67, #13 67, #14 67, #17 66, end

TL: 8.25M

Stopped by accident (annoying),  Discarded

Have to redo squire and GOL as there were no holes..!!! Annoying. Want to just give up.

This is not a great result: 66 when trying to beat 47..! Although it is better than the 79 (just).

Might be easier to modify the aligned 47 manually: see GOL alignedb

 - GOL aligned2 - 23:42 - 8  (3min) 97 via #1 97-> 23:48 Canceled (always the same result, seems pointless.)

For completion: Running, but not interested in progress anymore, only end result:

 - GOL aligned2 - 00:22 #2 88 #4 72 #5 69 #6 68 (00:58), #7 68 (01:00) #9 68, #10 68 (01:20) #12 67 #13 67 (01:42) #14 67 #15 67 (01:53) #16 66 #17 66 (02:04) #18 66 #19 66 #20 66 (02:20) end 66 (02:36)

TL: 8.13M

66 no good result. Also, still corrupted importing session back into KiCAD.!! Problem seems to be the HL5 - footprint issue? FUCKIT

Trying again, after having recreated HL5 (ungrouped). If this works (and it seems to have), then  re-group and paste the five holes in to the other GOL PCBs as they will all be corrupted:

 - GOL aligned2alsobad - 04:46 - 97 vias #1 97->88, #2 88->, #3 82->79, #4 78, #6 74 Aborted

HL5 was in wrong place, aborted. Shifted HL5 and started again:

 - GOL aligned2alsobad - 05:29 - 97 vias #1 97->89, #2 89->81, #3 77->74, #4 72 , end 66

TL: ???

Fix seems to work

Err/warn: 1/2

Rename aligned2alsobad -> aligned2a (as it is no longer bad, and to differenciate from aligned2, that has no holes, and it is a sister board layout of GOL aligned 2b)?

#### GOL aligned 2b 

Cloned from aligned2.
C10 above U5
Fixed HL5 issue, copied Holes from aligned2alsobad.

 - GOL aligned2b - 11:45 - Route  ? passes (? mins), ?vias, #1 86, #2 83->78, #3 70, #4 70 ->69, #5 69, #6 68, #7 68, #8 66(?)->65, #9 64, #10 63 (12:32), #11 63->62, #12 62 (12:39), #13 62->61, #14 61, #15 61, end 61 (12:53). 

TL: 7.9M-> 7.87M

This will have the same import hole issue. FIXED by copying Holes from aligned2alsobad!

Can save .dsn and autoroute, and at the same time change only silkscreen in KiCAD, and then import .ses without any mismatch issues? Yes!

Err/warn: 1/2

#### GOL alignedb

Cloned from aligned.
C10 below U5

Manually fixed, and holes added, and R8C1C2R14 closer - same as aligned but better.

One additional via for the GND to U5. The capacitor below made the each via necessary.

47->48 vias!

Err/warn: 1/2


Make manually fixed version with C10 above U5? -> alignedc

#### GOL alignedc

Cloned from alignedb.
C10 above U5

TODO: Make this (manually)


If I import into aligned, no problem, but the clone versions, with holes added, fail.
 - FIXED? Should be fixed now, was issue with HL5


#### RCBUS80r5cp3

Re-run to get a lower number of vias than 24 of RCBUS80r5cp/RCBUS80r5cp2
No components shifted
Clear board in freerouting and refill in KiCAD, before routing.
HL5 issue fixed again, by pasting in holes from GOLaligned2pc

 - RCBUS80r5cp3 - 21:48 (#16 stuck on 2 fails) (21:53 failed on 2 #8-#15) (21:57 fail on 2) (22:02 fail) 22:13 - Route  passes ( mins),  vias, #1 ,  end


Seems difficult to route, even though no components have been moved (RCBUS80r5cp was the same). Maybe easier to route with capacitor C10 under U5 instead of on top?

Aborted, will not route.

Remember to do: RCBUS80r5cp2a

#### RCBUS80r5cp4

Clone of RCBUS80r5cp3
Fixed crystals placement - only shifted crystals right next to caps - MUCH BETTER XTAL!!

 - RCBUS80r5cp4 - 22:21 - 7 passes (3 min), 53 via, #1 53->48, #2 44->40 (22:30), #3 36 (22:34), #4 36 (22:36), #5 36->35 (22:41), #6 35 (22:43), #7 35 (22:47), end. 35 (22:51)


TL: 6.89M -> 6.70M

Some DRC errors: DRC BAD

#### RCBUS80r5cp5

Clone of RCBUS80r5cp4

Fixed DRC errors: UART and Cap too close to HL5 – shifted UART and cap. XTAL overlapping R6. Shifted R6.
These DRC errors did not show up in RCBUS80r5cp/RCBUS80r5cp2 because the HL5 in those two PCBs was missing the pink ring of the courtyard, or foot print – it was missing one of its two parts. I had only copied over one component of the two components pertaining to a through hole.

 - This means that every previous HL5 is bad, need to check every prior PCB design that has holes!

 - RCBUS80r5cp5 - 23:01 - ~7 Passes (3 mins), 54 vias, #1 54->46, #2 46->45, #3 39->37, #4 37, #5 37 (23:21), #6 37 (23:24), #7 35 (23:28), end 35 (23:43).

TL: 6.87M

Err/Warn 1/0

A good board, nice correct placement and fixes. A good model. Just a bit of a high via count though.

One via under xtal could be routed with some rework, or swapping the jumpers J1 and J2 left and right


#### RCBUS80r5cp6

Clone of RCBUS80r5cp5
Just a rerun to get less than 35 vias. Maybe need to move C10?

 - RCBUS80r5cp6 00:41 54 vias, #1 54->48, #2 46, #3 37, #4 37,#6 37->35, #7 35, end 35 (01:14) Discarded.

Looks like the same result. Discarded.

01:15 #1 48, #2 45->41,  #3 40->37, #4 37, #7 35 (01:45), end 35 (1:45).


TL 6.87M

#### RCBUS80r5cp7

Clone of RCBUS80r5cp6
Just a rerun to get less than 35 vias. Maybe need to move C10?


02:43 - #1 50->49,#5 37, #6 37, 35 discarded

#### RCBUS80r5cp8

Clone of RCBUS80r5cp6
C10 below U5
Just a rerun to get less than 35 vias. Maybe need to move C10?

03:15: failed

Next move U5 right to edge of board.


 - RCBUS80r5cp8 - 03:22, ?? vias, #1 ??->43->42, #2 42->35 #6 33, #7 33, end 33 03:51

TL: 6.89M

TODO: Clone and rerun: RCBUS80r5cp8a

#### RCBUS80r5cp8a

Clone of RCBUS80r5cp8

 - RCBUS80r5cp8a - 04:31 -  ~8 passes (3 mins) 52 vias, #1 52->42, #2 42->37 (04:38), #3 34 (04:42), #5 34->33, #6 33, #7 33 (04:57), end 33 (05:00).

TL: 6.859M

Most of the vias seem to be between RAM and CPU, and under the CPU itself. Move ROM: RCBUS80r5cp10


#### RCBUS80r5cp9
Clone of RCBUS80r5cp8

Swapped RAM and cap (but gives less room betwen ROM and RAM)

 - RCBUS80r5cp9 - 03:56 - 04:01

Failed to route on 4 #18 twice

RAM moved back to right edge, cap below in empty area. CPU shifted right two clicks.

 - RCBUS80r5cp9 - 04:08 - 04:12 - 04:19 -  vias, 

Failed on 9! thrice! Fuckit!

Aborted


#### RCBUS80r5cp10
Clone of RCBUS80r5cp8

Shifted cap and ROM left 3 clicks

 - RCBUS80r5cp10 - 05:01 - 6, 45 vias, #1 45, end 45
 - RCBUS80r5cp10a - 05:06 - 6, 45 vias #1 45, #2 45, end 45 05:10
 - RCBUS80r5cp10b - 05:28 - 7, 45 vias #1 45, #2 45, end 45 05:32

Awful!!!

The A14 line to the jumper is not done!

Redo and do clear in freerouting process and reimport/reexport: RCBUS80r5cp10b - makes no difference!

If RCBUS80r5cp10b is the same then go back and examine RCBUS80r5cp2


### RCBUS80r5cp5a 

Clone of RCBUS80r5cp5
Moved UART left as much as possible as it wa moved right for the HL5
35 to beat

 - RCBUS80r5cp5a - 05:44 - 7 61 via, #1 61->56->??, #2 ??->50->47, #3 41 (06:04), #4 41->38, #6 38->37 (06:18), #7 37 (06:22), #8 37 (06:27), #9 37 (06:31), #10 37, end 37 (06:42) 

TL: 6.84M

Starts high! Ends high!

Could also move ROM and cap to the left three clicks: RCBUS80r5cp5a2

### RCBUS80r5cp5a2

Clone of RCBUS80r5cp5a
Shifted ROM and cap left 4 clicks.

 - RCBUS80r5cp5a2 - 06:42 - 06:47 - 9

Failed on 2 at #14  at #8/#9 twice! thrice?

If it doesn't route: Are these fails due to pin alignment?
Also try RCBUS80r5cp2 placement of UART and cap. Or try RCBUS80r5cp2 and (a) try to reproduce the 24 via, and (b) start from RCBUS80r5cp2 and slowly build up again, (manually?)
Or just move the hole, in all of the boards, including the recently completed GOL GOLaligned2pc: RCBUS80r5cp2h
 - Need to check for traces above HL5	

---

### Bad HL5 fixing: By shifting halfway down (not required)  - Start

#### RCBUS80r5cp2h
Cloned from RCBUS80r5cp2
New hole HL5 position, halfway down left side. New group

24 vias still. DRC_OK

#### RCBUS80r5cp2h2

TODO:

UART XTAL moved

#### RCBUS80r5cp2h3

CPU XTAL moved
C7 moved closer to U7

#### RCBUS80r5eh

Cloned RCBUS80r5e
New hole HL5 position, halfway down left side. New group
Changed hole group (new HL5 position)
TODO: Crystals not close to caps.

#### RCBUS40r3hh
Cloned RCBUS40r3h
New hole HL5 position, halfway down left side. New group
Changed hole group (new HL5 position)
TODO: Crystals not close to caps.

#### GOLalignedbh

Cloned GOLalignedb
New hole HL5 position, halfway down left side. New group
Changed hole group (new HL5 position)
Crystals not close to caps.

#### GOLaligned2pch

Cloned GOLaligned2pc
New hole HL5 position, halfway down left side. New group
Changed hole group (new HL5 position)


#### HL5 moved halfway down on 

 - RCBUS80r5cp2h3
 - RCBUS80r5eh
 - RCBUS40r3h (WIP)
   - RCBUS40r3hh (WIP)
 - GOLalignedb
   - GOLalignedbh
 - GOLaligned2pc
   - GOLaligned2pch

#### Bad HL5 fixing: By shifting halfway down (not required)  - End

---

#### RCBUS80r5cp2z

Cloned from RCBUS80r5cp2h
New hole HL5 position, just above previous (maintains stability). New group. 

But not required to move up at all..!!!

Just replacing the courtyardless HL5 with copy of HL1 seems to result in a better placed HL5 this time, no overlap? Why is z not complining DRC, but previouos "RCBUS80r5cp2" was? Which variant was it? It was RCBUS80r5cp2 and RCBUS80r5cp3. Can just move capacitor down C11 one notch. There is, nor ever was, no overlap with U11.
There seems to be a difference in position of C11 between RCBUS80r5cp2z and RCBUS80r5cp2/RCBUS80r5cp3.
Are the new HL5 positions needless..? RCBUS80r5cp2fixed is the same previous placement of HL5, with footprint/courtyard added, with no reulting DRC errors

Note: This RCBUS80r5cp2z is probably the same as RCBUS80r5cp2fixed. Not sure. RCBUS80r5cp2z should probably be discarded.

#### RCBUS80r5cp2fixed

Cloned RCBUS80r5cp2
Added footprint, courtyard to HL5
DRC good

#### RCBUS80r5cp2fixed2

Cloned RCBUS80r5cp2fixed

UART XTAL moved
CPU XTAL moved

This layout is now, probably, as good as the (near) perfect RCBUS80r5cp5

#### RCBUS80r5cp2fixed3

Cloned RCBUS80r5cp2fixed2

Joined two GND islands.

This is a now a CANDIDATE (late Aug)

#### RCBUS40r3i

Cloned from RCBUS40r3h

Hole HL5 fixed

Both XTALs moved perfect

This is a now a CANDIDATE (late Aug)



#### RCBUS80r5f

Cloned from RCBUS80r5e

Both XTALs moved perfect

This is a now a CANDIDATE (late Aug)


#### RCBUS40r3ip

Cloned from RCBUS40r3i

4 layer

 - RCBUS40r3ip - 07:35 - ~16 passes (3 mins), 48 vias, #1 48->43->??, #2 ??->42->33 (07:43), #3 33 (07:47), #4 33->32 (07:51), #5 32->31->?? (07:57), #6 ??->30 (08:05), #7 30 (08:14?), #8 30 (08:17), #9 30->24, #10 24->23 (8:30), end 21.

TL: 6.79M -> 6.57M

Hole 4 was routed over, at least during optim #1, was removed in optim #2. A slow start. Not a bad result. The hole was routed over again during #9, and made it in to the final result. Something is set incorrctly? No zone fill, holes drawn over.

Even running DRC does not fill the zones.

Rerun:

 - RCBUS40r3ip2 -  - ~ passes ( mins),  vias, #1 

Missing filled zones, make another: RCBUS40r3ipa


#### RCBUS40r3ipa

Cloned from RCBUS40r3i
Rerun and attempt to get filled zones.

4 layer (also no filled layers, why? Why does B not work?!)

 - RCBUS40r3ipa - 15:55 - ?? passes ( 3 mins), 48 vias, #1 48->43, #2 43->33 (16:03), #3 33 (16:08), #4 33->32->?? (16:11), #5 ?? -> 31->?? (16:16),  #6 ??->30 (16:20), #7 30, #8 ??, #9 ??->25->24 (16:31), #10 23->21 (16:36), #11 21 (16:41),  #12 21 (16:48), #13 21 (16:54), #14 21 (17:03), end 21 (17:09).

TL: 6.58M

Hole 4 route over agin (by #14, didn't notice when). Is this a clue as to why zones are not being filled?

#### RCBUS40r3ipb

Cloned from RCBUS40r3i
Rerun and attempt to get filled zones.

4 layer  (also no filled layers, why? Why does B not work?!)
Even doubling clicking the end of the filled zone, and B, it still does not show zones. Ae the zones there but not shown? Wierd! Every other board is ok, so why is this being a pain?

Abandonned, as only a zone test really. Not deleted, could be used in future.


#### Squires aligned4b2p

Cloned from Squires aligned4b2

4 layer 

Filled zones now look ok - need to double click when ending marking zone, before (B) fill?

Edge connector could be shifted up (also on aligned4b2)? Nah, no worries. It could be shifted, but it is ok, only silkscreen off board, the physical connector is (just about) on the board

 - Squires aligned4b2p - 17:10 - ? passes, (2 mins), 46 vias, #1 46->44-> ??, #2 ?? ->37->34 (17:17), #3 34->33->?? (17:17), #4 ??->30->29 (17:22), #5 29->?? (17:22), #6 ??->28 (17:24), #7 28 (17:28), end 28 (17:30).

TL: 6.55M

Not an impressive result, especially after a promising start, and only a 39 pin connector. Maybe shift up connector? -> aligned4b2pa?

The zones look different, on routed board. Not been refilled? What is happening? Why zone different today from yeterday and the day before? DRC auto refills zones? Maybe do the reimport empty board thing?

Actually running DRC brings filled zones back (although it does not for RCBUS40r3ip).

#### Squires aligned4b2p2

Rerun as Squires aligned4b2p2:

Cloned from Squires aligned4b2p

 - Squires aligned4b2p2 - 17:38 - passes (2 mins), 46 vias, #1 46->38->??, #2 ??->46->35->?? (17:45), #3 ??->34->33->32, (17:46), #4 32->30 (17:48), #5 29->28 (17:50), #6 28 (17:53), #7 28 (17:56), end 28 (17:58). 

TL: 6.548M

Effectively a duplicate result, abandonned as redundant.


#### Squires aligned4b2pa

Cloned from Squires aligned4b2p

Shifted up bus connector one notch
Reimport deleted traces from freerouting, refill zones, back into freerouting

 - Squires aligned4b2pa - 19:08 - 8 passes (3 mins), 45 vias, #1 45->43->??, #2 ??->38->37->33 (19:15), #3 ??->33->?? (19:17), #4 ??->32->30->?? (19:20), #6 ??->29 (19:27), #7 29 19:31, #8 29 (19:35), #9 29 (19:37), #10 ??, #11 25->24 (19:45), #12 24->23 (19:48), #13 23->22 (19:54), #14 22 (20:00), #15 22 (20:03), end 22 (20:07).



TL: 6.49M

Much better! Shifting up the connector was a good idea. Maybe do the same with Squires aligned4b2 (2 layers) and GOL align2pc2 (4 layers)? No, not for Squires aligned4b2, as it is a manual modification job.

DRC OK

Err/warn: 1/0



#### TTL Serial orientation

TTL Serial is the wrong way round!

#### Squires aligned4b5

Cloned from aligned4b4

1 via required for serial 54+1=55

FIXED.

Silkscreen fixes

#### Squire aligned4b6

Cloned from aligned4b5

Removed 1 via required for serial 49-1 = 48 

FIXED.

R10 and D4 placement adjusted.

CANDIDATE


#### GOL alignedd

Cloned from alignedc

1 via required for serial 48+1 = 49 

FIXED.

Silkscreen fixes

#### GOL alignede

Cloned from alignedd

Removed 1 via required for serial 49-1 = 48 

FIXED.

Silkscreen fixes

CANDIDATE

#### Squires aligned4b2pb

Cloned from aligned4b2pa
Swapped TTL connector. Autoroute:

 - aligned4b2pb - 01:53 failed on 2 - 01:56  failed on 2 - 02:01 (after re-import) (filed on 2)  -  passes (mins), vias , #1 , end.


Impossible to route. 

Shift RAM and cap up two notches

 - aligned4b2pb - 02:06 - 8 passes (3 mins), 51 vias, #1 51, #2 51, end 51

Terrible! Discarded

 02:12 - 51 same

Terrible! Discarded

Shift CPU right and up one notch
 
 - 02:18 - failed on 4 x 3 02:24 02:28

Impossible to route

Move CPU back to verify 51

 - 02:33 - failed on two! 

		

If fails, then just manually fix aligned4b2pa: aligned4b2pa2 or just replace this: aligned4b2pb

Given up. Abandoned. 


#### Squires aligned4b2pc

Cloned from aligned4b2pa

Manually fix TTL serial connector

Fixed, with no additional vias!

CANDIDATE

#### GOL aligned2pc3

Cloned from aligned2pc2

Manually fix TTL serial connector
Fixed, with no additional vias!

CANDIDATE


#### RCBUS40r3j

Cloned from RCBUS40r3i

Manually fix TTL serial connector
Fixed, with no additional vias!
TTL silkscreen changed to vertical
CANDIDATE

#### RCBUS80r5g

Cloned from RCBUS80r5f

Manually fix TTL serial connector
Fixed, with no additional vias!
TTL silkscreen changed to vertical
CANDIDATE


#### RCBUS80r5cp2fixed4

Cloned from RCBUS80r5cp2fixed3
Manually fix TTL serial connector
Fixed, with no additional vias!
TTL silkscreen changed to vertical
CANDIDATE



#### RCBUS40r3ip2

Cloned from RCBUS40r3ip

Manually fix TTL serial connector
Fixed, with no additional vias!
TTL silkscreen changed to vertical
CANDIDATE

But no planes!!!

##########################################################################################

I had two major hurdles: forgetting to place the mounting holes before finialising routing, and; the orientation of the TTL serial connector.

The first issue was solved by some manual re-routing. The same for the TTL serial connector. However, in the latter case, the orientation of the TTL serial connector in original layout by John Squires suited *his FTDI module*, as shown in [Flow Control for UART Serial communication between Z80 Playground and a PC](https://www.youtube.com/watch?v=RFxSKGnuisE) at [8:56](https://www.youtube.com/watch?v=RFxSKGnuisE), which has less common *reversed ordering* of the connectors. So, most fortuitously, it transpired that *my* original orientation of the connector was suitable for the more usual clone red FTDI module.

##########################################################################################


TODO: Check silkscreen of CH376S outline U10

Changed outline size: Moved: Left in from holes. Right in next to right edge of 02x08.
Moved down

TODO: check consistant position of disk LED (moved on GOL and squire down and right (one notch or two). But RCBUS40 has it well more to the right (and down a bit).

### CH375S adjusting


#### Squires aligned4b2paz

Cloned from aligned4b2pa (CANDIDATE)

OK, done
Err/Warn: 1/0
UART cap not in a good location, and not connected

#### Squires aligned4b2pcz

Cloned from aligned4b2pc

OK, done
Err/Warn: 1/0
UART cap not in a good location, and not connected



#### Squires aligned4b4z

Cloned from aligned4b4

Done ok

Err/Warn: 1/0

UART cap not in a good location, and not connected

#### Squires aligned4b6z

Cloned from aligned4b6

Done ok

Err/Warn: 1/0

UART cap not in a good location, and not connected

#### GOL aligned2pc2z

Cloned from aligned2pc2

Done ok

Err/Warn: 1/2

#### GOL aligned2pc3z

Cloned from aligned2pc3

Done ok

Err/Warn: 1/2


#### GOL alignedcz

Cloned from alignedc
Easy, just moved connector
Done ok

Err/Warn: 1/2

#### GOL alignedez

Cloned from alignede
Easy, just moved connector
Done ok

Err/Warn: 1/2


#### RCBUS40r3iz

Cloned from RCBUS40r3i

Easy, just moved connector
Done ok

Err/Warn: 1/4


#### RCBUS40r3jz

Cloned from RCBUS40r3j

Easy, just moved connector
Done ok

Err/Warn: 1/4

#### RCBUS40r3ipz

Cloned from RCBUS40r3ip

Easy, just moved connector
Done ok

Err/Warn: 1/4


#### RCBUS40r3ip2z

Cloned from RCBUS40r3ip2

Easy, just moved connector
Done ok

Err/Warn: 1/4


#### RCBUS80r5gz

Cloned from RCBUS80r5g

Easy, just moved connector
Done ok

Err/Warn: 1/7


#### RCBUS80r5fz

Cloned from RCBUS80r5f

Easy, just moved connector
Done ok

Err/Warn: 1/7

#### RCBUS80r5cp2fixed4z

Cloned from RCBUS80r5cp2fixed4

Easy, just moved connector
Done ok

Err/Warn: 1/7


#### RCBUS80r5cp2fixed3z

Cloned from RCBUS80r5cp2fixed3

Easy, just moved connector
Done ok

Err/Warn: 1/7


#### Squires aligned4b6z2

Cloned from aligned4b6z

Added via to Z80 VCC Cap

The new Squires RS2 candidate, replaces aligned4b6z


#### Bypass capacitors checked

See [Z80 Playground v1.2 - bypass capacitors](Z80%20Playground%20v1.2%20-%20bypass%20capacitors.md).




### Modifying a finished route

When modifying a finished DRC checked PCB layout, you can either: 

 - Delete *all traces* around the modification and then re-route
 - Start all over for the beginning, from an empty slate

The former may be quicker, but the latter might give a *better optimised solution*, with fewer vias.

## BOARDS TO LOOK AT

GOLr/f is *not* correctly placed C8 and J6/7 - DONE!
Squiresr/f is *not* correctly placed J6/7 - DONE!
Squiresr/f is *not* correctly placed C8
RCBUS40r/f is correctly placed C8 and J6/7
RCBUS80r/f is correctly placed C8 and J6/7

RCBUS are all ok: TODO check


<!-- Images -->

  [6]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_1.png "Z80 Playground v1.2 - PCB front#1"
  [7]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_2.png "Z80 Playground v1.2 - PCB front#2"
  [8]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_3.png "Z80 Playground v1.2 - PCB front#3"
  [9]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20rear_1.png "Z80 Playground v1.2 - PCB rear#1"

