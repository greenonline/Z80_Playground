# Z80 Playground v1.2 - routing status

Note: This is an historical list of routing attempts. See [PCB Candidates](documentation/Z80%20Playground%20v1.2%20-%20PCB%20candidates.md) for a more up-to-date, and final, list

---

The idea is to reduce the *via count* (V.C.). Anything below 65 vias is good, the lower the better - 65 is a semi-abitrary value chosen through empirical observation of over 40 autoroute processes.

Note `f` and `r` suffixes denote forward or reverse side placed bus connector – one orientation may be easier to route than the other.

- RCBUS
 - RCBUSr - tba
 - RCBUSf - tba
- RCBUS80r
 - RCBUS80r - 84 vias
 - RCBUS80r2 - 79 vias
 - RCBUS80r3 - 83 vias
 - RCBUS80r5 - 86 vias
 - RCBUS80r5c - 72 vias
 - RCBUS80r5d - 59 vias
 - RCBUS80r5e - 56 vias
 - RCBUS80r5f - 56 vias
 - RCBUS80r5g - 56 vias
 - RCBUS80r5cp - 24 vias (bad H5)
 - RCBUS80r5cp2h/2/3 - 24 vias (good H5)
 - RCBUS80r5cp5 - 35 vias (good board layout, bad V.C.)
 - RCBUS80r5cp2fixed3 - 24 vias
 - RCBUS80r5cp2fixed4 - 24 vias
- RCBUS80f
 - RCBUS80f - 93 vias
 - RCBUS80f2 - 94 vias
 - RCBUS80f3 - 98 vias
 - RCBUS80f4 - 87 vias
- RCBUS40r
 - RCBUS40r - 57 vias
 - RCBUS40r2 - 65 vias
 - RCBUS40r3 - 57 vias
 - RCBUS40r3a/b/c - 55 vias
 - RCBUS40r3d - 56 vias
 - RCBUS40r3e - 58 vias
 - RCBUS40r3f - 53 vias
 - RCBUS40r3g - 55 vias
 - RCBUS40r3h - 55 vias
 - RCBUS40r3i - 55 vias
 - RCBUS40r3j - 55 vias
 - RCBUS40r3ip - 21 vias
 - RCBUS40r3ip2 - 21 vias
- RCBUS40f
 - RCBUS40f - 77 vias
- RCBUS80/40
 - RCBUS80/40r - 69 vias
 - RCBUS80/40f - 95 vias

Garbage formatting and old attempts (historical?):

 - SQUIRESr - 66 vias*
 - SQUIRESr - 72 vias
 - SQUIRESr (aligned3) - 56 vias
 - SQUIRESf (aligned3) - 73 vias
 - SQUIRESr (aligned4) - 58 vias
 - SQUIRESr (aligned4a) - 54 vias
 - SQUIRESr (aligned4b4) - 54 vias
 - SQUIRESr (aligned4b5) - 55 vias
 - SQUIRESr (aligned4b6) - 54 vias
 - SQUIRESr (aligned4b2p) - 28 vias
   - Bus connector could be moved up a little, for better routing, 
     - otherwise a via will be needed
     - the edge connector isn't properly on the board!
 - SQUIRESr (aligned4b2pa) - 22 vias
 - SQUIRESr (aligned4b2pc) - 22 vias
 - SQUIRESf (aligned4) - 69 vias
 - GOL/MJr - 47 vias*
 - GOL/MJr - 47 vias
 - GOL/MJf - 79 vias

* not aligned

GOL hole issues:

 - GOLaligned - 47 vias
 - GOLaligned2 - 47 vias
 - GOLaligned2a - 66 vias
 - GOLaligned2b - 61 vias
 - GOLaligned2pb - 37 vias
 - GOLaligned2pc - 21 vias
 - GOLaligned2pc2 - 21 vias
 - GOLaligned2pc3 - 21 vias
 - GOLaligned3 - 63 vias
 - GOLaligned3a - 60 vias
 - GOLalignedb - 48 vias
 - GOLalignedc
 - GOLalignedd - 48 vias
 - GOLalignede - 48 vias

Squires hole issue:

 - 

Best:

 - SQUIRESr - 54 vias
 - SQUIRESf - 69 vias
 - GOL/MJr - 47 vias
 - GOL/MJf - 79 vias





