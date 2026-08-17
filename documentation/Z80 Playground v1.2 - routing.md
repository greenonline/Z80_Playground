# Z80 Playground v1.2 - routing

## Preamble

The Z80 Playground v1.2 routing, as derived from the images shown in the video, [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them](https://www.youtube.com/watch?v=MaolTlk7XKM).

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

##### Re-runs of Squiresr

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

##### Reruns RCBUS80r

Aim: to reduce below 84 vias. Historically high via count at start (>120):

 - RCBUS80r - 03:23 - Route ? passes (? mins), ?? vias, #1, end 94. Discarded
 - RCBUS80r - 11:45 - Route ? passes (? mins), 128 vias, #1 108, #2 107, #3 100, #4 95, #5 94, #6 94, #7 94, #8 94, #9 94, #10 94 (13:24), #11 94, #12 94 (13:41), #13 94, #14 94, (13:51), #15 94 (14:11), end 94 (14:20). Ultimately discarded.

##### Improvements to RCBUS(80r) layout: RCBUS80r3

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


##### Mounting holes: RCBUS80r2

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

##### Combined: RCBUS80r5

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

##### RCBUS80f <- RCBUS80r5c layout: RCBUS80f2

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

##### RCBU80f3: Minimal hole addition

Clone of RCBUS80f. Literally just paste in the holes and move the top XTAL. 

 - RCBUS80f3 - 03:11 - Route 13 passes (8 mins), 135 vias, #1 120 (119?), #2 119->105 (03:30), #3 105->102 (03:43), #4 102->101 (03:57), #5 101->101 (04:08), #6 101 (04:17), #7 101 (04:30) end 101 (07.40).

Trace length: 8.77M

Starts four vias higher than RCBUS80f (131, plus #1 115, #2 106, #3 99). Clearly the forward orientation of the bus is more difficult to route. 

Is this result an outlier? 101 vias seems rather high.

 Re-run as RCBUS80f3a - 11:53 - Route 17 passes (13 mins), 130 vias, #1 130->115, #2 115-> 107 (12:19), #3 107->106 (12:31), #4 106 (12:46), #5 105 (12:53), #6 104 (13:02), #7 104->103, (13:12), #8 103 (13:24), #9 100->99 (13:37), #10 99 (13:42), #11 99 (13:54), #12 99 *13:58), end.

Trace length: 8.86M->

A bit better, better than 101 at least, but still worse than 93/94.

If this is not good, then try the RCBUS80r5c changes, but without the IC shift.

##### RCBU80f4: Much realignment, but no IC shift

Clone of RCBUS80f. Shifted just one (top) XTAL, moved D5,D6, R14, reoriented R14, moved C7. Also shifted C10 on top of U5. Nice little change. Did not change ICs - that is the major difference from RCBU80f2.

Leveled C1 and C2, and moved closer together, as per the RCBUS80r3 change.

 - RCBUS80f4 - (07:40) - Route ? passes (? mins), ? vias, #1 ?, #2 ?, #20 87 (11:33), #21 87 (11:44), end 87 (11:52).

High trace length: 8.98M

A surprisingly good result, reducing 93 -> 87, by 6 vias.

##### Exercise in futility - RCBUS80f

These variants of RCBUS80f, the forward, or front, orientation of the RC2014bus connector, really are a very time-consuming exercise in futility as they merely serve to show, through their high number of vias (87-98), that the reverse, or rear, orientation of the RC2014 bus is more viable, resulting in (far) fewer vias.

Just focus on the RCBUS80r, and reducing via count below, the superlative, 72. Maybe also the RCBUS40r variant, for connection to simple motherboards, reducing from 56. RCBUS80f is 77 vias, so could try four variants again, as per RCBUS80f.


##### Fixing up RCBUS80r5c: RCBUS80r6

Fixed C1 and C2 not level. Easy manual fix. Still the same as RCBUS80r5c – no PCB changes.


##### RCBUS40r2 with holes

Cloned from RCBUS40r
R8C1C2R15 close together
Plus C7, C10 adjustments
Only top crystal shifted down.
Bus connector shifted down
No IC shift.

57 vias to beat:

 - RCBUS40r2 - Time - Route passes ( mins),  vias, #1, #2, end.



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



