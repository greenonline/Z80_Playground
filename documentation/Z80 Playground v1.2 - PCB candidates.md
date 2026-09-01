# Z80 Playground v1.2 - PCB candidates

 - RCBUS80r
   - 2 layer
     - RCBUS80r5fz
       - 56 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/7
     - RCBUS80r5gz
       - 56 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Error/Warn: 1/7
   - 4 layer
     - RCBUS80r5cp2fixed3z
       - 24 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/7
     - RCBUS80r5cp2fixed4z
       - 24 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Error/Warn: 1/7
 - RCBUS40r
   - 2 layer
     - RCBUS40r3iz
       - 55 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/4
     - RCBUS40r3jz
       - 55 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Error/Warn: 1/4
   - 4 layer
     - RCBUS40r3ipz
       - No filled zones, why?
       - 21 vias
       - Reverse TTL - Annotated
       - Error/Warn: 1/4
     - RCBUS40r3ip2z
       - No filled zones, why?
       - 21 vias
       - Good TTL - Annotated
       - Error/Warn: 1/4
 - Squires
   - 2 layer
     - aligned4b4z
       - 54 vias
       - XTALs both perfect
       - Bus connector could be moved up a little
       - 4 layer
       - Perfect!
       - Reverse TTL - Annotated
       - Error/Warn: 1/0
     - aligned4b6z
       - 54 vias
       - Good TTL - Annotated
       - Error/Warn: 1/0
     - aligned4b6z2
       - 55 vias
       - Good TTL - Annotated
       - Z80 caps good (required +1 via)
       - Error/Warn: 1/0
   - 4 layer
     - aligned4b2paz
       - 22 vias
       - Perfect!
       - Reverse TTL - Annotated
       - Error/Warn: 1/0
     - aligned4b2pcz
       - 22 vias
       - Perfect!
       - Good TTL - Annotated
       - Error/Warn: 1/0
 - GOL
   - 2 layer
     - GOL alignedcz
       - 48 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/2
     - GOL alignedez
       - 48 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Error/Warn: 1/2
   - 4 layer
     - GOL align2pc2z 
       - 21 vias
       - Reverse TTL - Annotated
       - XTALs both perfect
       - Bus connector could be moved up a little, for better routing, 
         - otherwise a via will be needed
         - the edge connector isn't properly on the board!
       - Error/Warn: 1/2
     - GOL align2pc3z 
       - 21 vias
       - Good TTL - Annotated
       - XTALs both perfect
       - Bus connector could be moved up a little, for better routing, 
         - otherwise a via will be needed
         - the edge connector isn't properly on the board!
       - Error/Warn: 1/2

Check:

 - XTALS next to caps?
 - C7 next to U7?
 - R8C1C2R15 close together
 - VCC and GND of each IC to bypass caps
 - LED labels rotated and close

 
 
Could just forget RCBUS40r and use RCBUS80r instead!
 
 
Notes:
 
 - The error, on all boards, is down to the wierd close placement of J1 and J2 on the CH376S board.
 
 
 
 
 