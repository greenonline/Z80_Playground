# Z80 Playground v1.2 - PCB candidates

## Preamble

A list of board and variant PCB candidates and via/err/warn table.
 
## Vanilla

TODO: Update since the NMI issue


 - RCBUS80r
   - 2 layer
     - RT2NPP: RCBUS80r5fz
       - 56 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/7
     - RT2NPP: RCBUS80r5fz2
       - 56 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/7
     - RT2NPP: RCBUS80r5fz4
       - 55 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Via removed to A8 on Bus pin 16
       - Error/Warn: 1/7
     - RT2NPP: RCBUS80r5fz5 -> RCBUS80r5fz6
       - 56 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - +1 via for ROM GND capacitor
       - Error/Warn: 1/7
     - RT2NPP: RCBUS80r5fz7
       - 55 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - -1 via IORQ pin on bus
       - Error/Warn: 1/7
     - RT2NPP: RCBUS80r5fz8
       - 54 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - -1 via D6 pin on bus
       - Error/Warn: 1/7
     - RT2NPP: RCBUS80r5fz9
       - 53 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - -1 via NMI pin on bus
       - Error/Warn: 1/7
     - RS2NPP: RCBUS80r5gz
       - 56 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Error/Warn: 1/7
     - RS2NPP: RCBUS80r5gz4
       - 55 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Via removed to A8 on Bus pin 16
       - Error/Warn: 1/7
     - RS2NPP: RCBUS80r5gz5 -> RCBUS80r5gz6
       - 56 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - +1 via for ROM GND capacitor
       - Error/Warn: 1/7
     - RS2NPP: RCBUS80r5gz7
       - 55 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - -1 via IORQ pin on bus
       - Error/Warn: 1/7
     - RS2NPP: RCBUS80r5gz8
       - 54 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - -1 via D6 pin on bus
       - Error/Warn: 1/7
     - RS2NPP: RCBUS80r5gz9
       - 53 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - -1 via NMI pin on bus
       - Error/Warn: 1/7
   - 4 layer
     - RT4NPP: RCBUS80r5cp2fixed3z
       - 25 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/7
     - RS4NPP: RCBUS80r5cp2fixed4z
       - 25 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Error/Warn: 1/7
 - RCBUS40r
   - 2 layer
     - RT2NPP: RCBUS40r3iz
       - 55 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/4
     - RT2NPP: RCBUS40r3iz6
       - 54 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - All bypass caps good
       - Error/Warn: 1/4
     - RT2NPP: RCBUS40r3iz7
       - 53 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - All bypass caps good
       - -1 via for GND U6
       - Error/Warn: 1/4
     - RS2NPP: RCBUS40r3jz
       - 55 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Error/Warn: 1/4
     - RS2NPP: RRCBUS40r3jz6
       - 54 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - All bypass caps good
       - Error/Warn: 1/4
     - RS2NPP: RRCBUS40r3jz7
       - 53 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - All bypass caps good
       - -1 via for GND U6
       - Error/Warn: 1/4
   - 4 layer
     - RT4NPP: RCBUS40r3ipz2
       - No filled zones, why?
       - 21 vias
       - Reverse TTL - Annotated
       - All bypass caps good
       - Error/Warn: 1/4
     - RS4NPP: RCBUS40r3ip2z2
       - No filled zones, why?
       - 21 vias
       - Good TTL - Annotated
       - All bypass caps good
       - Error/Warn: 1/4
 - Squires
   - 2 layer
     - RT2NPP: aligned4b4z2
       - 54 vias
       - XTALs both perfect
       - Bus connector could be moved up a little
       - Perfect!
       - Reverse TTL - Annotated
       - Error/Warn: 1/0
     - RT2NPP: aligned4b4z4
       - 55 vias
       - XTALs both perfect
       - Bus connector could be moved up a little
       - Perfect!
       - Reverse TTL - Annotated
       - Bypass caps done (RAM required +1 via)
       - Error/Warn: 1/0
     - RT2NPP: aligned4b4z5
       - 56 vias
       - XTALs both perfect
       - Bus connector could be moved up a little
       - Perfect!
       - Reverse TTL - Annotated
       - Bypass caps done (UART required +1 via)
       - Error/Warn: 1/0
     - RT2NPP: aligned4b4z6
       - 57 vias
       - XTALs both perfect
       - Bus connector could be moved up a little
       - Perfect!
       - Reverse TTL - Annotated
       - All bypass caps done (Z80 required +1 via)
       - Error/Warn: 1/0
     - RT2NPP: aligned4b4z7
       - 55 vias
       - XTALs both perfect
       - Bus connector could be moved up a little
       - Perfect!
       - Reverse TTL - Annotated
       - All bypass caps good
       - Removed -2 via
       - Error/Warn: 1/0
     - RT2NPP: aligned4b4z8
       - 54 vias
       - XTALs both perfect
       - Bus connector could be moved up a little
       - Perfect!
       - Reverse TTL - Annotated
       - All bypass caps good
       - Removed -1 via RAM (A7)
       - Error/Warn: 1/0
     - RS2NPP: aligned4b6z
       - 54 vias
       - Good TTL - Annotated
       - Error/Warn: 1/0
     - RS2NPP: aligned4b6z4
       - 55 vias
       - Good TTL - Annotated
       - Z80 caps good (required +1 via)
       - Error/Warn: 1/0
     - RS2NPP: aligned4b6z5
       - 56 vias
       - Good TTL - Annotated
       - RAM caps good (required +1 via)
       - Error/Warn: 1/0
     - RS2NPP: aligned4b6z6
       - 57 vias
       - Good TTL - Annotated
       - All bypass caps good (UART required +1 via)
       - Error/Warn: 1/0
     - RS2NPP: aligned4b6z7
       - 55 vias
       - Good TTL - Annotated
       - All bypass caps good
       - Removed -2 via
       - Error/Warn: 1/0
     - RS2NPP: aligned4b6z8
       - 54 vias
       - Good TTL - Annotated
       - All bypass caps good
       - Removed -1 via RAM (A7)
       - Error/Warn: 1/0
   - 4 layer
     - RT4NPP: aligned4b2paz
       - 22 vias
       - Perfect!
       - Reverse TTL - Annotated
       - Error/Warn: 1/0
     - RT4NPP: aligned4b2paz2
       - 21 vias
       - Perfect!
       - Reverse TTL - Annotated
       - Error/Warn: 1/0
     - RT4NPP: aligned4b2paz3
       - 20 vias
       - Perfect!
       - Reverse TTL - Annotated
       - Error/Warn: 1/0
     - RS4NPP: aligned4b2pcz
       - 22 vias
       - Perfect!
       - Good TTL - Annotated
       - Error/Warn: 1/0
     - RS4NPP: aligned4b2pcz2
       - 21 vias
       - Perfect!
       - Good TTL - Annotated
       - Error/Warn: 1/0
     - RS4NPP: aligned4b2pcz3
       - 20 vias
       - Perfect!
       - Good TTL - Annotated
       - Error/Warn: 1/0
 - GOL
   - 2 layer
     - RT2NPP: GOL alignedcz
       - 48 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Error/Warn: 1/2
     - RT2NPP: GOL alignedcz2-> alignedcz3
       - 49 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - Extra via for ROM GND bypass cap
       - Error/Warn: 1/2
     - RT2NPP: GOL alignedcz4
       - 48 vias
       - XTALs both perfect
       - Reverse TTL - Annotated
       - -1 via to U5 GND from U2 GND
       - All bypass caps good (U11?)
       - Error/Warn: 1/2
     - RS2NPP: GOL alignedez
       - 48 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Error/Warn: 1/2
     - RS2NPP: GOL alignedez2-> alignedez3
       - 49 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - Extra via for ROM GND bypass cap
       - Error/Warn: 1/2
     - RS2NPP: GOL alignedez4
       - 48 vias
       - XTALs both perfect
       - Good TTL - Annotated
       - -1 via to U5 GND from U2 GND
       - All bypass caps good (U11?)
       - Error/Warn: 1/2
   - 4 layer
     - RT4NPP: GOL align2pc2z 
       - 21 vias
       - Reverse TTL - Annotated
       - XTALs both perfect
       - Bus connector could be moved up a little, for better routing, 
         - otherwise a via will be needed
         - the edge connector isn't properly on the board!
       - Error/Warn: 1/2
     - RS4NPP: GOL align2pc3z 
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
 
 - The error, on all boards, is down to the weird close placement of J1 and J2 on the CH376S board.
 
 
 
 
### Bypass capacitor checks


See also [Z80 Playground v1.2 - bypass capacitors](Z80%20Playground%20v1.2%20-%20bypass%20capacitors.md) 

All Squires boards have acceptable bypass capacitors, now.

### CTS available

TODO: Update since the NMI issue


All PCB candidates, have a variant that adds CTS, just add an 'a' to the code.


 - MJ/GOL RS2CPP - alignedez4a 
   - Vias: 49
   - Err/Warn: 1/2
 - MJ/GOL RS4CPP - aligned2pc3za 
   - Vias: 22
   - Err/Warn: 1/2
 - MJ/GOL RT2CPP - alignedcz4a
   - Vias: 49
   - Err/Warn: 1/2
 - MJ/GOL RT4CPP - aligned2pc2za
   - Vias: 22
   - Err/Warn: 1/2
 - RCBUS40 RS2CPP - RCBUS40r3jz7a
   - Vias: 54
   - Err/Warn: 1/4
 - RCBUS40 RS4CPP - RCBUS40r3ip2z2a
   - Vias: 21
   - Err/Warn: 1/4
 - RCBUS40 RT2CPP - RCBUS40r3iz7a
   - Vias: 54
   - Err/Warn: 1/4
 - RCBUS40 RT4CPP - RCBUS40r3ipz2a
   - Vias: 21
   - Err/Warn: 1/4
 - RCBUS80 RS2CPP - RCBUS80r5gz9a
   - Vias: 54
   - Err/Warn: 1/7
 - RCBUS80 RS4CPP - RCBUS80r5cp2fixed4za
   - Vias: 25
   - Err/Warn: 1/7
 - RCBUS80 RT2CPP - RCBUS80r5fz9a
   - Vias: 54
   - Err/Warn: 1/7
 - RCBUS80 RT4CPP - RCBUS80r5cp2fixed3za
   - Vias: 25
   - Err/Warn: 1/7
 - Squires RS2CPP - aligned4b6z8a
   - Vias: 54
   - Err/Warn: 1/0
 - Squires RS4CPP - aligned4b2pcz3a
   - Vias: 20
   - Err/Warn: 1/0
 - Squires RT2CPP - aligned4b4z8a
   - Vias: 55
   - Err/Warn: 1/0
 - Squires RT4CPP - aligned4b2paz3a
   - Vias: 20
   - Err/Warn: 1/0
 
## Jumpered VCC

TODO: Update since the NMI issue


All derived from the non-`CTS` exposed boards:

 - MJ/GOL RS2NUP - alignedez4j 
   - Vias: 48
   - Err/Warn: 1/2
 - MJ/GOL RT2NUP - alignedcz4j
   - Vias: 48
   - Err/Warn: 1/2
 - MJ/GOL RS4NUP - aligned2pc3zj
   - Vias: 22
   - Err/Warn: 1/2
 - MJ/GOL RT4NUP - aligned2pc2zj
   - Vias: 22
   - Err/Warn: 1/2
 - RCBUS40 RS2NUP - RCBUS40r3jz7j
   - Vias: 53
   - Err/Warn: 1/4
 - RCBUS40 RS4NUP - RCBUS40r3ip2z2j
   - Vias: 21
   - Err/Warn: 1/4
 - RCBUS40 RT2NUP - RCBUS40r3iz7j
   - Vias: 53
   - Err/Warn: 1/4
 - RCBUS40 RT4NUP - RCBUS40r3ipz2j
   - Vias: 21
   - Err/Warn: 1/4
 - RCBUS80 RS2NUP - RCBUS80r5gz9j (derived from RCBUS80r5gz9)
   - Vias: 53
   - Error/Warn: 1/7
 - RCBUS80 RT2NUP - RCBUS80r5fz9j (derived from RCBUS80r5fz9)
   - Vias: 53
   - Error/Warn: 1/7
 - RCBUS80 RS4NUP: RCBUS80r5cp2fixed4zj
   - Vias: 25
   - Error/Warn: 1/7
 - RCBUS80 RT4NUP: RCBUS80r5cp2fixed3zj
   - Vias: 25
   - Error/Warn: 1/7
 - Squires RT2NUP - aligned4b4z8j
   - Vias: 54
   - Err/Warn: 1/0
 - Squires RS2NUP - aligned4b6z8j
   - Vias: 54
   - Err/Warn: 1/0
 - Squires RT4NUP - aligned4b2paz3j
   - Vias: 20
   - Err/Warn: 1/0
 - Squires RS4NUP - aligned4b2pcz3j
   - Vias: 20
   - Err/Warn: 1/0

## CTS & Jumpered VCC

TODO: Update since the NMI issue


All derived from the `CTS` exposed boards, version suffix `a`

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
 - RCBUS40 RS2CUP - RCBUS40r3jz7b
   - Vias: 54
   - Err/Warn: 1/4
 - RCBUS40 RS4CUP - RCBUS40r3ip2z2b
   - Vias: 21
   - Err/Warn: 1/4
 - RCBUS40 RT2CUP - RCBUS40r3iz7b
   - Vias: 54
   - Err/Warn: 1/4
 - RCBUS40 RT4CUP - RCBUS40r3ipz2b
   - Vias: 21
   - Err/Warn: 1/4
 - RCBUS80 RS2CUP - RCBUS80r5gz9b
   - Vias: 54
   - Err/Warn: 1/7
 - RCBUS80 RS4CUP - RCBUS80r5cp2fixed4zb
   - Vias: 25
   - Err/Warn: 1/7
 - RCBUS80 RT2CUP - RCBUS80r5fz9b
   - Vias: 54
   - Err/Warn: 1/7
 - RCBUS80 RT4CUP - RCBUS80r5cp2fixed3zb
   - Vias: 25
   - Err/Warn: 1/7
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

## Table

### Pre-VCC jumper (for historical reasons of via comparison)

| Board | Variant| Vias | Err | Warn |
|-------|--------|------|-----|------|
|       |        |      |     |      |
|Squires| RS2N   | 54   |  1  |   0  |
|Squires| RS2C   | 54   |  1  |   0  |
|Squires| RT2N   | 54   |  1  |   0  |
|Squires| RT2C   | 55   |  1  |   0  |
|Squires| RS4N   | 20   |  1  |   0  |
|Squires| RS4C   | 20   |  1  |   0  |
|Squires| RT4N   | 20   |  1  |   0  |
|Squires| RT4C   | 20   |  1  |   0  |
|MJ/GOL | RS2N   | 48   |  1  |   2  |
|MJ/GOL | RS2C   | 49   |  1  |   2  |
|MJ/GOL | RT2N   | 48   |  1  |   2  |
|MJ/GOL | RT2C   | 49   |  1  |   2  |
|MJ/GOL | RS4N   | 21   |  1  |   2  |
|MJ/GOL | RS4C   | 22   |  1  |   2  |
|MJ/GOL | RT4N   | 21   |  1  |   2  |
|MJ/GOL | RT4C   | 22   |  1  |   2  |
|RCBUS40| RS2N   | 53   |  1  |   4  |
|RCBUS40| RS2C   | 54   |  1  |   4  |
|RCBUS40| RT2N   | 53   |  1  |   4  |
|RCBUS40| RT2C   | 54   |  1  |   4  |
|RCBUS40| RS4N   | 21   |  1  |   4  |
|RCBUS40| RS4C   | 21   |  1  |   4  |
|RCBUS40| RT4N   | 21   |  1  |   4  |
|RCBUS40| RT4C   | 21   |  1  |   4  |
|RCBUS80| RS2N   | 53   |  1  |   7  |
|RCBUS80| RS2C   | 54   |  1  |   7  |
|RCBUS80| RT2N   | 53   |  1  |   7  |
|RCBUS80| RT2C   | 54   |  1  |   7  |
|RCBUS80| RS4N   | 25   |  1  |   7  |
|RCBUS80| RS4C   | 25   |  1  |   7  |
|RCBUS80| RT4N   | 25   |  1  |   7  |
|RCBUS80| RT4C   | 25   |  1  |   7  |


### Post NMI changes

| Board | Variant| Vias | Err | Warn |    Candidate          |
|-------|--------|------|-----|------|-----------------------|
|       |        |      |     |      |                       |
|Squires| RS2NPP | 54   |  1  |   0  | aligned4b6z8n         |
|Squires| RS2NPN | -    |  -  |   -  |    N/A                |
|Squires| RS2NUP | 54   |  1  |   0  | aligned4b6z8jn        |
|Squires| RS2NUN | -    |  -  |   -  |    N/A                |
|Squires| RS2CPP | 54   |  1  |   0  | aligned4b6z8an        |
|Squires| RS2CPN | -    |  -  |   -  |    N/A                |
|Squires| RS2CUP | 54   |  1  |   0  |  aligned4b6z8bn       |
|Squires| RS2CUN | 54   |  1  |   0  |    TBA                |
|Squires| RT2NPP | 54   |  1  |   0  |  aligned4b4z8n        |
|Squires| RT2NPN | -    |  -  |   -  |    N/A                |
|Squires| RT2NUP | 54   |  1  |   0  |  aligned4b4z8jn       |
|Squires| RT2NUN | -    |  -  |   -  |    N/A                |
|Squires| RT2CPP | 55   |  1  |   0  |  aligned4b4z8an       |
|Squires| RT2CPN | -    |  -  |   -  |    N/A                |
|Squires| RT2CUP | 55   |  1  |   0  |  aligned4b4z8bn       |
|Squires| RT2CUN | 55   |  1  |   0  |    TBA                |
|Squires| RS4NPP | 20   |  1  |   0  | aligned4b2pcz3n       |
|Squires| RS4NPN | -    |  -  |   -  |    N/A                |
|Squires| RS4NUP | 20   |  1  |   0  | aligned4b2pcz3jn      |
|Squires| RS4NUN | -    |  -  |   -  |    N/A                |
|Squires| RS4CPP | 20   |  1  |   0  | aligned4b2pcz3an      |
|Squires| RS4CPN | -    |  -  |   -  |    N/A                |
|Squires| RS4CUP | 20   |  1  |   0  | aligned4b2pcz3bn      |
|Squires| RS4CUN | 20   |  1  |   0  |    TBA                |
|Squires| RT4NPP | 20   |  1  |   0  | aligned4b2paz3n       |
|Squires| RT4NPN | -    |  -  |   -  |    N/A                |
|Squires| RT4NUP | 20   |  1  |   0  | aligned4b2paz3jn      |
|Squires| RT4NUN | -    |  -  |   -  |    N/A                |
|Squires| RT4CPP | 20   |  1  |   0  | aligned4b2paz3an      |
|Squires| RT4CPN | -    |  -  |   -  |    N/A                |
|Squires| RT4CUP | 20   |  1  |   0  | aligned4b2paz3bn      |
|Squires| RT4CUN | 20   |  1  |   0  |    TBA                |
|       |        |      |     |      |                       |
|MJ/GOL | RS2NPP | 48   |  1  |   2  | alignedez4n           |
|MJ/GOL | RS2NPN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2NUP | 48   |  1  |   2  | alignedez4jn          |
|MJ/GOL | RS2NUN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2CPP | 49   |  1  |   2  | alignedez4an          |
|MJ/GOL | RS2CPN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2CUP | 49   |  1  |   2  | alignedez4bn          |
|MJ/GOL | RS2CUN | -    |  1  |   2  |    TBA                |
|MJ/GOL | RT2NPP | 48   |  1  |   2  | alignedcz4n           |
|MJ/GOL | RT2NPN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2NUP | 48   |  1  |   2  | alignedcz4jn          |
|MJ/GOL | RT2NUN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2CPP | 49   |  1  |   2  | alignedcz4an          |
|MJ/GOL | RT2CPN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2CUP | 49   |  1  |   2  | alignedcz4bn          |
|MJ/GOL | RT2CUN | -    |  1  |   2  |    TBA                |
|MJ/GOL | RS4NPP | 21   |  1  |   2  | aligned2pc3zn         |
|MJ/GOL | RS4NPN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4NUP | 21   |  1  |   2  | aligned2pc3znj        |
|MJ/GOL | RS4NUN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4CPP | 21   |  1  |   2  | aligned2pc3zan        |
|MJ/GOL | RS4CPN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4CUP | 21   |  1  |   2  | aligned2pc3zbn        |
|MJ/GOL | RS4CUN | -    |  1  |   2  |    TBA                |
|MJ/GOL | RT4NPP | 21   |  1  |   2  | aligned2pc2zn         |
|MJ/GOL | RT4NPN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4NUP | 21   |  1  |   2  | aligned2pc2zjn        |
|MJ/GOL | RT4NUN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4CPP | 21   |  1  |   2  | aligned2pc2zan        |
|MJ/GOL | RT4CPN | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4CUP | 21   |  1  |   2  | aligned2pc2zbn        |
|MJ/GOL | RT4CUN | -    |  1  |   2  |    TBA                |
|       |        |      |     |      |                       |
|RCBUS40| RS2NPP | 53   |  1  |   4  | RCBUS40r3jz7          |
|RCBUS40| RS2NPN | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2NUP | 53   |  1  |   4  | RCBUS40r3jz7j         |
|RCBUS40| RS2NUN | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2CPP | 54   |  1  |   4  | RCBUS40r3jz7a         |
|RCBUS40| RS2CPN | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2CUP | 54   |  1  |   4  | RCBUS40r3jz7b         |
|RCBUS40| RS2CUN | -    |  1  |   4  |    TBA                |
|RCBUS40| RT2NPP | 53   |  1  |   4  | RCBUS40r3iz7          |
|RCBUS40| RT2NPN | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2NUP | 53   |  1  |   4  | RCBUS40r3iz7j         |
|RCBUS40| RT2NUN | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2CPP | 54   |  1  |   4  | RCBUS40r3iz7a         |
|RCBUS40| RT2CPN | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2CUP | 54   |  1  |   4  | RCBUS40r3iz7b         |
|RCBUS40| RT2CUN | -    |  1  |   4  |    TBA                |
|RCBUS40| RS4NPP | 20   |  1  |   4  | RCBUS40r3ip2z2        |
|RCBUS40| RS4NPN | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4NUP | 20   |  1  |   4  | RCBUS40r3ip2z2j       |
|RCBUS40| RS4NUN | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4CPP | 20   |  1  |   4  | RCBUS40r3ip2z2a       |
|RCBUS40| RS4CPN | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4CUP | 20   |  1  |   4  | RCBUS40r3ip2z2b       |
|RCBUS40| RS4CUN | -    |  1  |   4  |    TBA                |
|RCBUS40| RT4NPP | 20   |  1  |   4  | RCBUS40r3ipz2         |
|RCBUS40| RT4NPN | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4NUP | 20   |  1  |   4  | RCBUS40r3ipz2j        |
|RCBUS40| RT4NUN | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4CPP | 20   |  1  |   4  | RCBUS40r3ipz2a        |
|RCBUS40| RT4CPN | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4CUP | 20   |  1  |   4  | RCBUS40r3ipz2b        |
|RCBUS40| RT4CUN | -    |  1  |   4  |    TBA                |
|       |        |      |     |      |                       |
|RCBUS80| RS2NPP | 55   |  1  |   7  | RCBUS80r5gz9n         |
|RCBUS80| RS2NPN | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2NUP | 55   |  1  |   7  | RCBUS80r5gz9jn        |
|RCBUS80| RS2NUN | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2CPP | 56   |  1  |   7  | RCBUS80r5gz9an        |
|RCBUS80| RS2CPN | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2CUP | 56   |  1  |   7  | RCBUS80r5gz9bn        |
|RCBUS80| RS2CUN | 61   |  1  |   7  | RCBUS80r5gz9bp        |
|RCBUS80| RT2NPP | 55   |  1  |   7  | RCBUS80r5fz9n         |
|RCBUS80| RT2NPN | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2NUP | 55   |  1  |   7  | RCBUS80r5fz9jn        |
|RCBUS80| RT2NUN | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2CPP | 56   |  1  |   7  | RCBUS80r5fz9an        |
|RCBUS80| RT2CPN | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2CUP | 56   |  1  |   7  | RCBUS80r5fz9bn        |
|RCBUS80| RT2CUN | 61   |  1  |   7  | RCBUS80r5fz9bp        |
|RCBUS80| RS4NPP | 24   |  1  |   7  | RCBUS80r5cp2fixed4zn  |
|RCBUS80| RS4NPN | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4NUP | 24   |  1  |   7  | RCBUS80r5cp2fixed4zjn |
|RCBUS80| RS4NUN | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4CPP | 24   |  1  |   7  | RCBUS80r5cp2fixed4zan |
|RCBUS80| RS4CPN | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4CUP | 24   |  1  |   7  | RCBUS80r5cp2fixed4zbn |
|RCBUS80| RS4CUN | 24   |  1  |   7  | RCBUS80r5cp2fixed4zbm |
|RCBUS80| RT4NPP | 24   |  1  |   7  | RCBUS80r5cp2fixed3zn  |
|RCBUS80| RT4NPN | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4NUP | 24   |  1  |   7  | RCBUS80r5cp2fixed3zjn |
|RCBUS80| RT4NUN | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4CPP | 24   |  1  |   7  | RCBUS80r5cp2fixed3zan |
|RCBUS80| RT4CPN | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4CUP | 24   |  1  |   7  | RCBUS80r5cp2fixed3zbn |
|RCBUS80| RT4CUN | 24   |  1  |   7  | RCBUS80r5cp2fixed3zbm |
|       |        |      |     |      |                       |

### Post /RAMEN changes

NOTE: While the RCBUS80 was derived from CUNF variant, the RCBUS40 was derived from the CUPF variant, as the NMI fix has not (yet) been applied to the RCBU40 board as NMI is not routed to the RCBUS 40 bus, only the RCBUS80 bus.

| Board | Variant | Vias | Err | Warn |    Candidate          |
|-------|---------|------|-----|------|-----------------------|
|       |         |      |     |      |                       |
|Squires| RS2NPPF | 54   |  1  |   0  | aligned4b6z8n         |
|Squires| RS2NPNF | -    |  -  |   -  |    N/A                |
|Squires| RS2NUPF | 54   |  1  |   0  | aligned4b6z8jn        |
|Squires| RS2NUNF | -    |  -  |   -  |    N/A                |
|Squires| RS2CPPF | 54   |  1  |   0  | aligned4b6z8an        |
|Squires| RS2CPNF | -    |  -  |   -  |    N/A                |
|Squires| RS2CUPF | 54   |  1  |   0  |  aligned4b6z8bn       |
|Squires| RS2CUNF | 54   |  1  |   0  |    TBA                |
|Squires| RT2NPPF | 54   |  1  |   0  |  aligned4b4z8n        |
|Squires| RT2NPNF | -    |  -  |   -  |    N/A                |
|Squires| RT2NUPF | 54   |  1  |   0  |  aligned4b4z8jn       |
|Squires| RT2NUNF | -    |  -  |   -  |    N/A                |
|Squires| RT2CPPF | 55   |  1  |   0  |  aligned4b4z8an       |
|Squires| RT2CPNF | -    |  -  |   -  |    N/A                |
|Squires| RT2CUPF | 55   |  1  |   0  |  aligned4b4z8bn       |
|Squires| RT2CUNF | 55   |  1  |   0  |    TBA                |
|Squires| RS4NPPF | 20   |  1  |   0  | aligned4b2pcz3n       |
|Squires| RS4NPNF | -    |  -  |   -  |    N/A                |
|Squires| RS4NUPF | 20   |  1  |   0  | aligned4b2pcz3jn      |
|Squires| RS4NUNF | -    |  -  |   -  |    N/A                |
|Squires| RS4CPPF | 20   |  1  |   0  | aligned4b2pcz3an      |
|Squires| RS4CPNF | -    |  -  |   -  |    N/A                |
|Squires| RS4CUPF | 20   |  1  |   0  | aligned4b2pcz3bn      |
|Squires| RS4CUNF | 20   |  1  |   0  |    TBA                |
|Squires| RT4NPPF | 20   |  1  |   0  | aligned4b2paz3n       |
|Squires| RT4NPNF | -    |  -  |   -  |    N/A                |
|Squires| RT4NUPF | 20   |  1  |   0  | aligned4b2paz3jn      |
|Squires| RT4NUNF | -    |  -  |   -  |    N/A                |
|Squires| RT4CPPF | 20   |  1  |   0  | aligned4b2paz3an      |
|Squires| RT4CPNF | -    |  -  |   -  |    N/A                |
|Squires| RT4CUPF | 20   |  1  |   0  | aligned4b2paz3bn      |
|Squires| RT4CUNF | 20   |  1  |   0  |    TBA                |
|       |         |      |     |      |                       |
|MJ/GOL | RS2NPPF | 48   |  1  |   2  | alignedez4n           |
|MJ/GOL | RS2NPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2NUPF | 48   |  1  |   2  | alignedez4jn          |
|MJ/GOL | RS2NUNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2CPPF | 49   |  1  |   2  | alignedez4an          |
|MJ/GOL | RS2CPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2CUPF | 49   |  1  |   2  | alignedez4bn          |
|MJ/GOL | RS2CUNF | -    |  1  |   2  |    TBA                |
|MJ/GOL | RT2NPPF | 48   |  1  |   2  | alignedcz4n           |
|MJ/GOL | RT2NPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2NUPF | 48   |  1  |   2  | alignedcz4jn          |
|MJ/GOL | RT2NUNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2CPPF | 49   |  1  |   2  | alignedcz4an          |
|MJ/GOL | RT2CPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2CUPF | 49   |  1  |   2  | alignedcz4bn          |
|MJ/GOL | RT2CUNF | -    |  1  |   2  |    TBA                |
|MJ/GOL | RS4NPPF | 21   |  1  |   2  | aligned2pc3zn         |
|MJ/GOL | RS4NPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4NUPF | 21   |  1  |   2  | aligned2pc3znj        |
|MJ/GOL | RS4NUNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4CPPF | 21   |  1  |   2  | aligned2pc3zan        |
|MJ/GOL | RS4CPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4CUPF | 21   |  1  |   2  | aligned2pc3zbn        |
|MJ/GOL | RS4CUNF | -    |  1  |   2  |    TBA                |
|MJ/GOL | RT4NPPF | 21   |  1  |   2  | aligned2pc2zn         |
|MJ/GOL | RT4NPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4NUPF | 21   |  1  |   2  | aligned2pc2zjn        |
|MJ/GOL | RT4NUNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4CPPF | 21   |  1  |   2  | aligned2pc2zan        |
|MJ/GOL | RT4CPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4CUPF | 21   |  1  |   2  | aligned2pc2zbn        |
|MJ/GOL | RT4CUNF | -    |  1  |   2  |    TBA                |
|       |         |      |     |      |                       |
|RCBUS40| RS2NPPF | 53   |  1  |   4  | RCBUS40r3jz7          |
|RCBUS40| RS2NPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2NUPF | 53   |  1  |   4  | RCBUS40r3jz7j         |
|RCBUS40| RS2NUNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2CPPF | 54   |  1  |   4  | RCBUS40r3jz7a         |
|RCBUS40| RS2CPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2CUPF | 54   |  1  |   4  | RCBUS40r3jz7b         |
|RCBUS40| RS2CUPS | 54   |  1  |   4  | RCBUS40r3jz7b2        |
|RCBUS40| RS2CUNF | -    |  1  |   4  |    TBA                |
|RCBUS40| RT2NPPF | 53   |  1  |   4  | RCBUS40r3iz7          |
|RCBUS40| RT2NPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2NUPF | 53   |  1  |   4  | RCBUS40r3iz7j         |
|RCBUS40| RT2NUNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2CPPF | 54   |  1  |   4  | RCBUS40r3iz7a         |
|RCBUS40| RT2CPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2CUPF | 54   |  1  |   4  | RCBUS40r3iz7b         |
|RCBUS40| RT2CUPS | 54   |  1  |   4  | RCBUS40r3iz7b2        |
|RCBUS40| RT2CUNF | -    |  1  |   4  |    TBA                |
|RCBUS40| RS4NPPF | 20   |  1  |   4  | RCBUS40r3ip2z2        |
|RCBUS40| RS4NPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4NUPF | 20   |  1  |   4  | RCBUS40r3ip2z2j       |
|RCBUS40| RS4NUNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4CPPF | 20   |  1  |   4  | RCBUS40r3ip2z2a       |
|RCBUS40| RS4CPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4CUPF | 20   |  1  |   4  | RCBUS40r3ip2z2b       |
|RCBUS40| RS4CUPS | 20   |  1  |   4  | RCBUS40r3ip2z2b2      |
|RCBUS40| RS4CUNF | -    |  1  |   4  |    TBA                |
|RCBUS40| RT4NPPF | 20   |  1  |   4  | RCBUS40r3ipz2         |
|RCBUS40| RT4NPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4NUPF | 20   |  1  |   4  | RCBUS40r3ipz2j        |
|RCBUS40| RT4NUNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4CPPF | 20   |  1  |   4  | RCBUS40r3ipz2a        |
|RCBUS40| RT4CPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4CUPF | 20   |  1  |   4  | RCBUS40r3ipz2b        |
|RCBUS40| RT4CUPS | 20   |  1  |   4  | RCBUS40r3ipz2b2       |
|RCBUS40| RT4CUNF | -    |  1  |   4  |    TBA                |
|       |         |      |     |      |                       |
|RCBUS80| RS2NPPF | 55   |  1  |   7  | RCBUS80r5gz9n         |
|RCBUS80| RS2NPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2NUPF | 55   |  1  |   7  | RCBUS80r5gz9jn        |
|RCBUS80| RS2NUNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2CPPF | 56   |  1  |   7  | RCBUS80r5gz9an        |
|RCBUS80| RS2CPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2CUPF | 56   |  1  |   7  | RCBUS80r5gz9bn        |
|RCBUS80| RS2CUNF | 61   |  1  |   7  | RCBUS80r5gz9bp        |
|RCBUS80| RS2CUNS | 61   |  1  |   7  | RCBUS80r5gz9bp2       |
|RCBUS80| RT2NPPF | 55   |  1  |   7  | RCBUS80r5fz9n         |
|RCBUS80| RT2NPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2NUPF | 55   |  1  |   7  | RCBUS80r5fz9jn        |
|RCBUS80| RT2NUNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2CPPF | 56   |  1  |   7  | RCBUS80r5fz9an        |
|RCBUS80| RT2CPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2CUPF | 56   |  1  |   7  | RCBUS80r5fz9bn        |
|RCBUS80| RT2CUNF | 61   |  1  |   7  | RCBUS80r5fz9bp        |
|RCBUS80| RT2CUNS | 61   |  1  |   7  | RCBUS80r5fz9bp2       |
|RCBUS80| RS4NPPF | 24   |  1  |   7  | RCBUS80r5cp2fixed4zn  |
|RCBUS80| RS4NPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4NUPF | 24   |  1  |   7  | RCBUS80r5cp2fixed4zjn |
|RCBUS80| RS4NUNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4CPPF | 24   |  1  |   7  | RCBUS80r5cp2fixed4zan |
|RCBUS80| RS4CPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4CUPF | 24   |  1  |   7  | RCBUS80r5cp2fixed4zbn |
|RCBUS80| RS4CUNF | 24   |  1  |   7  | RCBUS80r5cp2fixed4zbm |
|RCBUS80| RS4CUNS | 24   |  1  |   7  | RCBUS80r5cp2fixed4zbm2|
|RCBUS80| RT4NPPF | 24   |  1  |   7  | RCBUS80r5cp2fixed3zn  |
|RCBUS80| RT4NPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4NUPF | 24   |  1  |   7  | RCBUS80r5cp2fixed3zjn |
|RCBUS80| RT4NUNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4CPPF | 24   |  1  |   7  | RCBUS80r5cp2fixed3zan |
|RCBUS80| RT4CPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4CUPF | 24   |  1  |   7  | RCBUS80r5cp2fixed3zbn |
|RCBUS80| RT4CUNF | 24   |  1  |   7  | RCBUS80r5cp2fixed3zbm |
|RCBUS80| RT4CUNS | 24   |  1  |   7  | RCBUS80r5cp2fixed3zb02|
|       |         |      |     |      |                       |


### With `aligned` and `fixed` removed

But Squire and MJ/GOL now need a pre-fix, seeing that the prior prefix `aligned` has been removed?

| Board | Variant | Vias | Err | Warn |    Candidate          |
|-------|---------|------|-----|------|-----------------------|
|       |         |      |     |      |                       |
|Squires| RS2NPPF | 54   |  1  |   0  | 4b6z8n         |
|Squires| RS2NPNF | -    |  -  |   -  |    N/A                |
|Squires| RS2NUPF | 54   |  1  |   0  | 4b6z8jn        |
|Squires| RS2NUNF | -    |  -  |   -  |    N/A                |
|Squires| RS2CPPF | 54   |  1  |   0  | 4b6z8an        |
|Squires| RS2CPNF | -    |  -  |   -  |    N/A                |
|Squires| RS2CUPF | 54   |  1  |   0  |  4b6z8bn       |
|Squires| RS2CUNF | 54   |  1  |   0  |    TBA                |
|Squires| RT2NPPF | 54   |  1  |   0  |  4b4z8n        |
|Squires| RT2NPNF | -    |  -  |   -  |    N/A                |
|Squires| RT2NUPF | 54   |  1  |   0  |  4b4z8jn       |
|Squires| RT2NUNF | -    |  -  |   -  |    N/A                |
|Squires| RT2CPPF | 55   |  1  |   0  |  4b4z8an       |
|Squires| RT2CPNF | -    |  -  |   -  |    N/A                |
|Squires| RT2CUPF | 55   |  1  |   0  |  4b4z8bn       |
|Squires| RT2CUNF | 55   |  1  |   0  |    TBA                |
|Squires| RS4NPPF | 20   |  1  |   0  | 4b2pcz3n       |
|Squires| RS4NPNF | -    |  -  |   -  |    N/A                |
|Squires| RS4NUPF | 20   |  1  |   0  | 4b2pcz3jn      |
|Squires| RS4NUNF | -    |  -  |   -  |    N/A                |
|Squires| RS4CPPF | 20   |  1  |   0  | 4b2pcz3an      |
|Squires| RS4CPNF | -    |  -  |   -  |    N/A                |
|Squires| RS4CUPF | 20   |  1  |   0  | 4b2pcz3bn      |
|Squires| RS4CUNF | 20   |  1  |   0  |    TBA                |
|Squires| RT4NPPF | 20   |  1  |   0  | 4b2paz3n       |
|Squires| RT4NPNF | -    |  -  |   -  |    N/A                |
|Squires| RT4NUPF | 20   |  1  |   0  | 4b2paz3jn      |
|Squires| RT4NUNF | -    |  -  |   -  |    N/A                |
|Squires| RT4CPPF | 20   |  1  |   0  | 4b2paz3an      |
|Squires| RT4CPNF | -    |  -  |   -  |    N/A                |
|Squires| RT4CUPF | 20   |  1  |   0  | 4b2paz3bn      |
|Squires| RT4CUNF | 20   |  1  |   0  |    TBA                |
|       |         |      |     |      |                       |
|MJ/GOL | RS2NPPF | 48   |  1  |   2  | ez4n           |
|MJ/GOL | RS2NPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2NUPF | 48   |  1  |   2  | ez4jn          |
|MJ/GOL | RS2NUNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2CPPF | 49   |  1  |   2  | ez4an          |
|MJ/GOL | RS2CPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS2CUPF | 49   |  1  |   2  | ez4bn          |
|MJ/GOL | RS2CUNF | -    |  1  |   2  |    TBA                |
|MJ/GOL | RT2NPPF | 48   |  1  |   2  | cz4n           |
|MJ/GOL | RT2NPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2NUPF | 48   |  1  |   2  | cz4jn          |
|MJ/GOL | RT2NUNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2CPPF | 49   |  1  |   2  | cz4an          |
|MJ/GOL | RT2CPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT2CUPF | 49   |  1  |   2  | cz4bn          |
|MJ/GOL | RT2CUNF | -    |  1  |   2  |    TBA                |
|MJ/GOL | RS4NPPF | 21   |  1  |   2  | 2pc3zn         |
|MJ/GOL | RS4NPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4NUPF | 21   |  1  |   2  | 2pc3znj        |
|MJ/GOL | RS4NUNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4CPPF | 21   |  1  |   2  | 2pc3zan        |
|MJ/GOL | RS4CPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RS4CUPF | 21   |  1  |   2  | 2pc3zbn        |
|MJ/GOL | RS4CUNF | -    |  1  |   2  |    TBA                |
|MJ/GOL | RT4NPPF | 21   |  1  |   2  | 2pc2zn         |
|MJ/GOL | RT4NPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4NUPF | 21   |  1  |   2  | 2pc2zjn        |
|MJ/GOL | RT4NUNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4CPPF | 21   |  1  |   2  | 2pc2zan        |
|MJ/GOL | RT4CPNF | -    |  -  |   -  |    N/A                |
|MJ/GOL | RT4CUPF | 21   |  1  |   2  | 2pc2zbn        |
|MJ/GOL | RT4CUNF | -    |  1  |   2  |    TBA                |
|       |         |      |     |      |                       |
|RCBUS40| RS2NPPF | 53   |  1  |   4  | RCBUS40r3jz7          |
|RCBUS40| RS2NPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2NUPF | 53   |  1  |   4  | RCBUS40r3jz7j         |
|RCBUS40| RS2NUNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2CPPF | 54   |  1  |   4  | RCBUS40r3jz7a         |
|RCBUS40| RS2CPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS2CUPF | 54   |  1  |   4  | RCBUS40r3jz7b         |
|RCBUS40| RS2CUPS | 54   |  1  |   4  | RCBUS40r3jz7b2        |
|RCBUS40| RS2CUNF | -    |  1  |   4  |    TBA                |
|RCBUS40| RT2NPPF | 53   |  1  |   4  | RCBUS40r3iz7          |
|RCBUS40| RT2NPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2NUPF | 53   |  1  |   4  | RCBUS40r3iz7j         |
|RCBUS40| RT2NUNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2CPPF | 54   |  1  |   4  | RCBUS40r3iz7a         |
|RCBUS40| RT2CPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT2CUPF | 54   |  1  |   4  | RCBUS40r3iz7b         |
|RCBUS40| RT2CUPS | 54   |  1  |   4  | RCBUS40r3iz7b2        |
|RCBUS40| RT2CUNF | -    |  1  |   4  |    TBA                |
|RCBUS40| RS4NPPF | 20   |  1  |   4  | RCBUS40r3ip2z2        |
|RCBUS40| RS4NPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4NUPF | 20   |  1  |   4  | RCBUS40r3ip2z2j       |
|RCBUS40| RS4NUNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4CPPF | 20   |  1  |   4  | RCBUS40r3ip2z2a       |
|RCBUS40| RS4CPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RS4CUPF | 20   |  1  |   4  | RCBUS40r3ip2z2b       |
|RCBUS40| RS4CUPS | 20   |  1  |   4  | RCBUS40r3ip2z2b2      |
|RCBUS40| RS4CUNF | -    |  1  |   4  |    TBA                |
|RCBUS40| RT4NPPF | 20   |  1  |   4  | RCBUS40r3ipz2         |
|RCBUS40| RT4NPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4NUPF | 20   |  1  |   4  | RCBUS40r3ipz2j        |
|RCBUS40| RT4NUNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4CPPF | 20   |  1  |   4  | RCBUS40r3ipz2a        |
|RCBUS40| RT4CPNF | -    |  -  |   -  |    N/A                |
|RCBUS40| RT4CUPF | 20   |  1  |   4  | RCBUS40r3ipz2b        |
|RCBUS40| RT4CUPS | 20   |  1  |   4  | RCBUS40r3ipz2b2       |
|RCBUS40| RT4CUNF | -    |  1  |   4  |    TBA                |
|       |         |      |     |      |                       |
|RCBUS80| RS2NPPF | 55   |  1  |   7  | RCBUS80r5gz9n         |
|RCBUS80| RS2NPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2NUPF | 55   |  1  |   7  | RCBUS80r5gz9jn        |
|RCBUS80| RS2NUNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2CPPF | 56   |  1  |   7  | RCBUS80r5gz9an        |
|RCBUS80| RS2CPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS2CUPF | 56   |  1  |   7  | RCBUS80r5gz9bn        |
|RCBUS80| RS2CUNF | 61   |  1  |   7  | RCBUS80r5gz9bp        |
|RCBUS80| RS2CUNS | 61   |  1  |   7  | RCBUS80r5gz9bp2       |
|RCBUS80| RT2NPPF | 55   |  1  |   7  | RCBUS80r5fz9n         |
|RCBUS80| RT2NPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2NUPF | 55   |  1  |   7  | RCBUS80r5fz9jn        |
|RCBUS80| RT2NUNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2CPPF | 56   |  1  |   7  | RCBUS80r5fz9an        |
|RCBUS80| RT2CPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT2CUPF | 56   |  1  |   7  | RCBUS80r5fz9bn        |
|RCBUS80| RT2CUNF | 61   |  1  |   7  | RCBUS80r5fz9bp        |
|RCBUS80| RT2CUNS | 61   |  1  |   7  | RCBUS80r5fz9bp2       |
|RCBUS80| RS4NPPF | 24   |  1  |   7  | RCBUS80r5cp24zn  |
|RCBUS80| RS4NPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4NUPF | 24   |  1  |   7  | RCBUS80r5cp24zjn |
|RCBUS80| RS4NUNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4CPPF | 24   |  1  |   7  | RCBUS80r5cp24zan |
|RCBUS80| RS4CPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RS4CUPF | 24   |  1  |   7  | RCBUS80r5cp24zbn |
|RCBUS80| RS4CUNF | 24   |  1  |   7  | RCBUS80r5cp24zbm |
|RCBUS80| RS4CUNS | 24   |  1  |   7  | RCBUS80r5cp24zbm2|
|RCBUS80| RT4NPPF | 24   |  1  |   7  | RCBUS80r5cp23zn  |
|RCBUS80| RT4NPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4NUPF | 24   |  1  |   7  | RCBUS80r5cp23zjn |
|RCBUS80| RT4NUNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4CPPF | 24   |  1  |   7  | RCBUS80r5cp23zan |
|RCBUS80| RT4CPNF | -    |  -  |   -  |    N/A                |
|RCBUS80| RT4CUPF | 24   |  1  |   7  | RCBUS80r5cp23zbn |
|RCBUS80| RT4CUNF | 24   |  1  |   7  | RCBUS80r5cp23zbm |
|RCBUS80| RT4CUNS | 24   |  1  |   7  | RCBUS80r5cp23zb02|
|       |         |      |     |      |                       |

### Notes on the variants

The variant is a four character code, i.e. `RT2C`, denoting features:

 - R/F - reverse or front mounted bus (only reverse mounted available)
 - S/T - orientation of the TTL serial port (use the `T` variant for the red FTDI TTL serial board, see [Z80 Playground v1.2 - serial/power module](Z80%20Playground%20v1.2%20-%20serial-power%20module.md) for more details. Note: it is important to chose the correct variant)
 - 2/4 - 2- or 4-layer board
 - C/N - CTS exposed on TTL serial pins or not
 - U/P - Serial VCC is jumpered or not (Unpowered/Powered)
 - P/N - Positive or negative edge triggered NMI
 - F/S - Fixed or switchable RAM
 
## Templates (do not use)

```
| Board | Variant| Vias | Err | Warn |
|-------|--------|------|-----|------|
|       |        |      |     |      |
|Squires| RS2N   |      |     |      |
|Squires| RS2C   |      |     |      |
|Squires| RT2N   |      |     |      |
|Squires| RT2C   |      |     |      |
|Squires| RS4N   |      |     |      |
|Squires| RS4C   |      |     |      |
|Squires| RT4N   |      |     |      |
|Squires| RT4C   |      |     |      |
|MJ/GOL | RS2N   |      |     |      |
|MJ/GOL | RS2C   |      |     |      |
|MJ/GOL | RT2N   |      |     |      |
|MJ/GOL | RT2C   |      |     |      |
|MJ/GOL | RS4N   |      |     |      |
|MJ/GOL | RS4C   |      |     |      |
|MJ/GOL | RT4N   |      |     |      |
|MJ/GOL | RT4C   |      |     |      |
|RCBUS40| RS2N   |      |     |      |
|RCBUS40| RS2C   |      |     |      |
|RCBUS40| RT2N   |      |     |      |
|RCBUS40| RT2C   |      |     |      |
|RCBUS40| RS4N   |      |     |      |
|RCBUS40| RS4C   |      |     |      |
|RCBUS40| RT4N   |      |     |      |
|RCBUS40| RT4C   |      |     |      |
|RCBUS80| RS2N   |      |     |      |
|RCBUS80| RS2C   |      |     |      |
|RCBUS80| RT2N   |      |     |      |
|RCBUS80| RT2C   |      |     |      |
|RCBUS80| RS4N   |      |     |      |
|RCBUS80| RS4C   |      |     |      |
|RCBUS80| RT4N   |      |     |      |
|RCBUS80| RT4C   |      |     |      |
```

Extended table template

```none
| Board | Variant| Vias | Err | Warn | Candidate |
|-------|--------|------|-----|------|-----------|
|       |        |      |     |      |           |
|Squires| RS2NPP | 54   |  1  |   0  |           |
|Squires| RS2NPN | -    |  -  |   -  |           |
|Squires| RS2NUP | 54   |  1  |   0  |           |
|Squires| RS2NUN | -    |  -  |   -  |           |
|Squires| RS2CPP | 54   |  1  |   0  |           |
|Squires| RS2CPN | -    |  -  |   -  |           |
|Squires| RS2CUP | 54   |  1  |   0  |           |
|Squires| RS2CUN | 54   |  1  |   0  |           |
|Squires| RT2NPP | 54   |  1  |   0  |           |
|Squires| RT2NPN | -    |  -  |   -  |           |
|Squires| RT2NUP | 54   |  1  |   0  |           |
|Squires| RT2NUN | -    |  -  |   -  |           |
|Squires| RT2CPP | 55   |  1  |   0  |           |
|Squires| RT2CPN | -    |  -  |   -  |           |
|Squires| RT2CUP | 55   |  1  |   0  |           |
|Squires| RT2CUN | 55   |  1  |   0  |           |
|Squires| RS4NPP | 20   |  1  |   0  |           |
|Squires| RS4NPN | -    |  -  |   -  |           |
|Squires| RS4NUP | 20   |  1  |   0  |           |
|Squires| RS4NUN | -    |  -  |   -  |           |
|Squires| RS4CPP | 20   |  1  |   0  |           |
|Squires| RS4CPN | -    |  -  |   -  |           |
|Squires| RS4CUP | 20   |  1  |   0  |           |
|Squires| RS4CUN | 20   |  1  |   0  |           |
|Squires| RT4NPP | 20   |  1  |   0  |           |
|Squires| RT4NPN | -    |  -  |   -  |           |
|Squires| RT4NUP | 20   |  1  |   0  |           |
|Squires| RT4NUN | -    |  -  |   -  |           |
|Squires| RT4CPP | 20   |  1  |   0  |           |
|Squires| RT4CPN | -    |  -  |   -  |           |
|Squires| RT4CUP | 20   |  1  |   0  |           |
|Squires| RT4CUN | 20   |  1  |   0  |           |
|       |        |      |     |      |           |
|MJ/GOL | RS2NPP | -    |  1  |   2  |           |
|MJ/GOL | RS2NPN | -    |  -  |   -  |           |
|MJ/GOL | RS2NUP | -    |  1  |   2  |           |
|MJ/GOL | RS2NUN | -    |  -  |   -  |           |
|MJ/GOL | RS2CPP | -    |  1  |   2  |           |
|MJ/GOL | RS2CPN | -    |  -  |   -  |           |
|MJ/GOL | RS2CUP | -    |  1  |   2  |           |
|MJ/GOL | RS2CUN | -    |  1  |   2  |           |
|MJ/GOL | RT2NPP | -    |  1  |   2  |           |
|MJ/GOL | RT2NPN | -    |  -  |   -  |           |
|MJ/GOL | RT2NUP | -    |  1  |   2  |           |
|MJ/GOL | RT2NUN | -    |  -  |   -  |           |
|MJ/GOL | RT2CPP | -    |  1  |   2  |           |
|MJ/GOL | RT2CPN | -    |  -  |   -  |           |
|MJ/GOL | RT2CUP | -    |  1  |   2  |           |
|MJ/GOL | RT2CUN | -    |  1  |   2  |           |
|MJ/GOL | RS4NPP | -    |  1  |   2  |           |
|MJ/GOL | RS4NPN | -    |  -  |   -  |           |
|MJ/GOL | RS4NUP | -    |  1  |   2  |           |
|MJ/GOL | RS4NUN | -    |  -  |   -  |           |
|MJ/GOL | RS4CPP | -    |  1  |   2  |           |
|MJ/GOL | RS4CPN | -    |  -  |   -  |           |
|MJ/GOL | RS4CUP | -    |  1  |   2  |           |
|MJ/GOL | RS4CUN | -    |  1  |   2  |           |
|MJ/GOL | RT4NPP | -    |  1  |   2  |           |
|MJ/GOL | RT4NPN | -    |  -  |   -  |           |
|MJ/GOL | RT4NUP | -    |  1  |   2  |           |
|MJ/GOL | RT4NUN | -    |  -  |   -  |           |
|MJ/GOL | RT4CPP | -    |  1  |   2  |           |
|MJ/GOL | RT4CPN | -    |  -  |   -  |           |
|MJ/GOL | RT4CUP | -    |  1  |   2  |           |
|MJ/GOL | RT4CUN | -    |  1  |   2  |           |
|       |        |      |     |      |           |
|RCBUS40| RS2NPP | -    |  1  |   4  |           |
|RCBUS40| RS2NPN | -    |  -  |   -  |           |
|RCBUS40| RS2NUP | -    |  1  |   4  |           |
|RCBUS40| RS2NUN | -    |  -  |   -  |           |
|RCBUS40| RS2CPP | -    |  1  |   4  |           |
|RCBUS40| RS2CPN | -    |  -  |   -  |           |
|RCBUS40| RS2CUP | -    |  1  |   4  |           |
|RCBUS40| RS2CUN | -    |  1  |   4  |           |
|RCBUS40| RT2NPP | -    |  1  |   4  |           |
|RCBUS40| RT2NPN | -    |  -  |   -  |           |
|RCBUS40| RT2NUP | -    |  1  |   4  |           |
|RCBUS40| RT2NUN | -    |  -  |   -  |           |
|RCBUS40| RT2CPP | -    |  1  |   4  |           |
|RCBUS40| RT2CPN | -    |  -  |   -  |           |
|RCBUS40| RT2CUP | -    |  1  |   4  |           |
|RCBUS40| RT2CUN | -    |  1  |   4  |           |
|RCBUS40| RS4NPP | -    |  1  |   4  |           |
|RCBUS40| RS4NPN | -    |  -  |   -  |           |
|RCBUS40| RS4NUP | -    |  1  |   4  |           |
|RCBUS40| RS4NUN | -    |  -  |   -  |           |
|RCBUS40| RS4CPP | -    |  1  |   4  |           |
|RCBUS40| RS4CPN | -    |  -  |   -  |           |
|RCBUS40| RS4CUP | -    |  1  |   4  |           |
|RCBUS40| RS4CUN | -    |  1  |   4  |           |
|RCBUS40| RT4NPP | -    |  1  |   4  |           |
|RCBUS40| RT4NPN | -    |  -  |   -  |           |
|RCBUS40| RT4NUP | -    |  1  |   4  |           |
|RCBUS40| RT4NUN | -    |  -  |   -  |           |
|RCBUS40| RT4CPP | -    |  1  |   4  |           |
|RCBUS40| RT4CPN | -    |  -  |   -  |           |
|RCBUS40| RT4CUP | -    |  1  |   4  |           |
|RCBUS40| RT4CUN | -    |  1  |   4  |           |
|       |        |      |     |      |           |
|RCBUS80| RS2NPP | -    |  1  |   7  |           |
|RCBUS80| RS2NPN | -    |  -  |   -  |           |
|RCBUS80| RS2NUP | -    |  1  |   7  |           |
|RCBUS80| RS2NUN | -    |  -  |   -  |           |
|RCBUS80| RS2CPP | -    |  1  |   7  |           |
|RCBUS80| RS2CPN | -    |  -  |   -  |           |
|RCBUS80| RS2CUP | -    |  1  |   7  |           |
|RCBUS80| RS2CUN | -    |  1  |   7  |           |
|RCBUS80| RT2NPP | -    |  1  |   7  |           |
|RCBUS80| RT2NPN | -    |  -  |   -  |           |
|RCBUS80| RT2NUP | -    |  1  |   7  |           |
|RCBUS80| RT2NUN | -    |  -  |   -  |           |
|RCBUS80| RT2CPP | -    |  1  |   7  |           |
|RCBUS80| RT2CPN | -    |  -  |   -  |           |
|RCBUS80| RT2CUP | -    |  1  |   7  |           |
|RCBUS80| RT2CUN | -    |  1  |   7  |           |
|RCBUS80| RS4NPP | -    |  1  |   7  |           |
|RCBUS80| RS4NPN | -    |  -  |   -  |           |
|RCBUS80| RS4NUP | -    |  1  |   7  |           |
|RCBUS80| RS4NUN | -    |  -  |   -  |           |
|RCBUS80| RS4CPP | -    |  1  |   7  |           |
|RCBUS80| RS4CPN | -    |  -  |   -  |           |
|RCBUS80| RS4CUP | -    |  1  |   7  |           |
|RCBUS80| RS4CUN | -    |  1  |   7  |           |
|RCBUS80| RT4NPP | -    |  1  |   7  |           |
|RCBUS80| RT4NPN | -    |  -  |   -  |           |
|RCBUS80| RT4NUP | -    |  1  |   7  |           |
|RCBUS80| RT4NUN | -    |  -  |   -  |           |
|RCBUS80| RT4CPP | -    |  1  |   7  |           |
|RCBUS80| RT4CPN | -    |  -  |   -  |           |
|RCBUS80| RT4CUP | -    |  1  |   7  |           |
|RCBUS80| RT4CUN | -    |  1  |   7  |           |
|       |        |      |     |      |           |
```
 
## Notes

- Negative NMI makes no sense on RCBUS40 as NMI not routed to bus
- Switchable RAM makes little sense on Squires and GOL
