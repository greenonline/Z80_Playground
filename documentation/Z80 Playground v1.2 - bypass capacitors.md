# Z80 Playground v1.2 - bypass capacitors 


|Board| U1 VCC | U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|Squires RT2| VIA | VIA | OK | C10 | OK | C9 | OK | OK | OK | C9 | OK | OK | OK | C9 | OK | C8/C12 |
|Squires RS2| VIA | VIA | OK | C10 | OK | C9 | OK | OK | OK | C9 | OK | OK | OK | OK | OK | C8 |
|Squires RT4| OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK |
|Squires RS4| OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK |
|GOL RT2| VIA | C12 | OK | C10 | OK | C12 | OK | OK | OK | C9 | OK | OK | OK | C9 | OK | C8 |
|GOL RS2| VIA | C12 | OK | C10 | OK | C12 | OK | OK | OK | C9 | OK | OK | OK | C9 | OK | C8 |
|GOL RT4| VIA | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK |
|GOL RS4| VIA | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK |
|RCBUS80 RT2| OK | C12 | OK | C10 | OK | C8 | OK | OK | OK | C9 | OK | C8 | OK | C9 | OK | C8 |
|RCBUS80 RS2| OK| C12 | OK | C10 | OK | C8 |  OK | OK | OK | C9 | OK | C8 | OK | C9 | OK | C8 |
|RCBUS80 RT4| VIA | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK |
|RCBUS80 RS4| VIA | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK | OK |
|RCBUS40 RT2| OK | C12 | OK | C10 | OK | C9 | OK | OK | OK | VIA | OK | C8 | OK | VIA | OK | C8/C12 |
|RCBUS40 RS2| OK | C12 | OK | C10 | OK | C9 | OK | OK | OK | VIA | OK | C8 | OK | OK | OK | C8/C12 |
|RCBUS40 RT4| OK | OK | OK | OK | OK | C12 | OK | OK | OK | OK | OK | OK | OK | OK | OK | NO |
|RCBUS40 RS4| OK | OK | OK | OK | OK | C12 | OK | OK | OK | OK | OK | OK | OK | NO | OK | NO |

where,

 - Squires RT2 = aligned4b4z
 - Squires RS2 = aligned4b6z2
 - Squires RT4 = aligned4b2paz
 - Squires RS4 = aligned4b2pcz
 - GOL RT2 = alignedcz
 - GOL RS2 = alignedez
 - GOL RT4 = aligned2pc2z
 - GOL RS4 = aligned2pc3z
 - RCBUS80 RT2 = RCBUS80r5fz
 - RCBUS80 RS2 = RCBUS80r5gz
 - RCBUS80 RT4 = RCBUS80r5cp2fixed3z
 - RCBUS80 RS4 = RCBUS80r5cp2fixed4z
 - RCBUS40 RT2 = RCBUS40r3iz
 - RCBUS40 RS2 = RCBUS40r3jz
 - RCBUS40 RT4 = RCBUS40r3ipz
 - RCBUS40 RS4 = RCBUS40r3ip2z


ICs

 - U1 - Z80 - C9
 - U2 - RAM - C12
 - U3 - ROM - C3
 - U5 - 7432 - C10
 - U6 - 7432 - C13
 - U7 - 7414 - C7
 - U8 - 7402 - C4
 - U10 - USB card
 - U11 - UART - C11


## Notes

 - RCBUS80 RS2, RT2, RS4, RT4:  U8 IC label missing in center of IC
 - RCBUS40 RS2, RT2, RS4, RT4:  U8 IC label missing in center of IC
 - RCBUS40 RS2, RT2: Possible, using via, to route U7 GND
 - Squires - 2 layers - may be possible to route U6 GND, if C4 moved close to U6
 - TODO: Check why Squires RS2 required extra via for VCC pushing to 55? Why Squires RT2 has only 54?



## Template (DO NOT USE!!!)

```none

|Board| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|Squires RT2| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|Squires RS2| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|Squires RT4| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|Squires RS4| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|GOL RT2| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|GOL RS2| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|GOL RT4| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC |  U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|GOL RS4| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|RCBUS80 RT2| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|RCBUS80 RS2| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|RCBUS80 RT4| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|RCBUS80 RS4| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|RCBUS40 RT2| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|RCBUS40 RS2| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|RCBUS40 RT4| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
|RCBUS40 RS4| U1 VCC| U1 GND | U2 VCC | U2 GND | U3 VCC | U3 GND | U5 VCC | U5 GND | U6 VCC | U6 GND | U7 VCC | U7 GND | U8 VCC | U8 GND | U11 VCC | U11 GND |
```