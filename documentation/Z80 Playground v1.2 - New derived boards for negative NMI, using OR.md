# Z80 Playground v1.2 - New derived boards for negative NMI, using OR

# NOTE: All boards with a `c` sufix are bad, as they are based on the faulty OR logic (needs to be NOR)

Power jumper and cts derived from CTS, change the `a` suffix to a `b` suffix

power jumper only derived from PCB candidates - take the board for CTS and remove the 'a' suffix

Inverse NMI derived from VCC jumper and CTS, change the `b` suffix to a `c` suffix

RCBUS80 

 - RCBUS80 RS2CUP - RCBUS80r5gz9b
   - Vias: 54
   - Err/Warn: 1/7
 - RCBUS80 RS4CUP - RCBUS80r5cp2fixed4zb (reduced via to A10) 24 vias (and all others)
   - Vias: 25
   - Err/Warn: 1/7
 - RCBUS80 RT2CUP - RCBUS80r5fz9b
   - Vias: 54
   - Err/Warn: 1/7
 - RCBUS80 RT4CUP - RCBUS80r5cp2fixed3zb (reduced via to A10) 24 vias (and all others)
   - Vias: 25
   - Err/Warn: 1/7



 - RCBUS80 RS2CUN - RCBUS80r5gz9c ***schematic*** PCB not easy!
   - Vias: 54
   - Err/Warn: 1/7
 - RCBUS80 RS4CUN - RCBUS80r5cp2fixed4zc  ***schematic*** PCB not easy! 1/7 25>24
 via
   - Vias: 25
   - Err/Warn: 1/7
 - RCBUS80 RT2CUN - RCBUS80r5fz9c  ***schematic*** PCB not easy!
   - Vias: 54
   - Err/Warn: 1/7
 - RCBUS80 RT4CUN - RCBUS80r5cp2fixed3zc ***schematic*** PCB not easy! 1/7 25>24 via
   - Vias: 25
   - Err/Warn: 1/7


RCBUS40


 - RCBUS40 RS2CUP - RCBUS40r3jz7b
   - Vias: 54
   - Err/Warn: 1/4
 - RCBUS40 RS4CUP - RCBUS40r3ip2z2b   (reduced via to NMI pad) 20 vias (and all others)
   - Vias: 21
   - Err/Warn: 1/4
 - RCBUS40 RT2CUP - RCBUS40r3iz7b 
   - Vias: 54
   - Err/Warn: 1/4
 - RCBUS40 RT4CUP - RCBUS40r3ipz2b    (reduced via to NMI pad) 20 vias (and all others)
   - Vias: 21
   - Err/Warn: 1/4



 - RCBUS40 RS2CUN - RCBUS40r3jz7c ***schematic*** PCB not easy!
   - Vias: 54
   - Err/Warn: 1/4
 - RCBUS40 RS4CUN - RCBUS40r3ip2z2c ***schematic*** PCB not easy! 1/4 21>20 vias
   - Vias: 21
   - Err/Warn: 1/4
 - RCBUS40 RT2CUN - RCBUS40r3iz7c ***schematic*** PCB not easy!
   - Vias: 54
   - Err/Warn: 1/4
 - RCBUS40 RT4CUN - RCBUS40r3ipz2c ***schematic*** PCB not easy! 1/4 21>20 vias
   - Vias: 21
   - Err/Warn: 1/4


MJ/GOL_

 - MJ/GOL RS2CUP - alignedez4b 
   - Vias: 49
   - Err/Warn: 1/2
 - MJ/GOL RS4CUP - aligned2pc3zb 
   - Vias: 22
   - Err/Warn: 1/2
 - MJ/GOL RT2CUP - alignedcz4b
   - Vias: 49
   - Err/Warn: 1/2
 - MJ/GOL RT4CUP - aligned2pc2zb
   - Vias: 22
   - Err/Warn: 1/2


 - MJ/GOL RS2CUN - alignedez4c **schematic**
   - Vias: 49
   - Err/Warn: 1/2
 - MJ/GOL RS4CUN - aligned2pc3zc **schematic**
   - Vias: 22
   - Err/Warn: 1/2
 - MJ/GOL RT2CUN - alignedcz4c **schematic**
   - Vias: 49
   - Err/Warn: 1/2
 - MJ/GOL RT4CUN - aligned2pc2zc **schematic**
   - Vias: 22
   - Err/Warn: 1/2


Squires

 - Squires RS2CUP - aligned4b6z8b
   - Vias: 54
   - Err/Warn: 1/0
 - Squires RS4CUP - aligned4b2pcz3b
   - Vias: 20
   - Err/Warn: 1/0
 - Squires RT2CUP - aligned4b4z8b
   - Vias: 55
   - Err/Warn: 1/0
 - Squires RT4CUP - aligned4b2paz3b
   - Vias: 20
   - Err/Warn: 1/0



 - Squires RS2CUN - aligned4b6z8c  **schematic**
   - Vias: 54
   - Err/Warn: 1/0
 - Squires RS4CUN - aligned4b2pcz3c **schematic**
   - Vias: 20
   - Err/Warn: 1/0
 - Squires RT2CUN - aligned4b4z8c **schematic**
   - Vias: 55
   - Err/Warn: 1/0
 - Squires RT4CUN - aligned4b2paz3c **schematic**
   - Vias: 20
   - Err/Warn: 1/0


The logic won't work, logic OR is not correct! Wired-OR, is it AND?