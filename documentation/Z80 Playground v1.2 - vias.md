# Z80 Playground v1.2 - vias

## Table

|Board      | Vias |
|-----------|------|
|Squires RT2| 54   | 
|Squires RS2| 54   | 
|Squires RT4| 20   | 
|Squires RS4| 20   | 
|MJ/GOL RT2 | 48   | 
|MJ/GOL RS2 | 48   |
|MJ/GOL RT4 | 22   | 
|MJ/GOL RS4 | 22   | 
|RCBUS80 RT2| 53   | 
|RCBUS80 RS2| 53   | 
|RCBUS80 RT4| 25   | 
|RCBUS80 RS4| 25   | 
|RCBUS40 RT2| 53   | 
|RCBUS40 RS2| 53   | 
|RCBUS40 RT4| 21   | 
|RCBUS40 RS4| 21   | 



where,

 - Squires RT2 = aligned4b4z6 -> aligned4b4z8
 - Squires RS2 = aligned4b6z6 -> aligned4b6z8
 - Squires RT4 = aligned4b2paz -> aligned4b2paz3
 - Squires RS4 = aligned4b2pcz -> aligned4b2pcz3
 - MJ/GOL RT2  = alignedcz -> alignedcz2 -> alignedcz4
 - MJ/GOL RS2  = alignedez -> alignedez2
 - MJ/GOL RT4  = aligned2pc2z
 - MJ/GOL RS4  = aligned2pc3z
 - RCBUS80 RT2 = RCBUS80r5fz9
 - RCBUS80 RS2 = RCBUS80r5gz9
 - RCBUS80 RT4 = RCBUS80r5cp2fixed3z
 - RCBUS80 RS4 = RCBUS80r5cp2fixed4z
 - RCBUS40 RT2 = RCBUS40r3iz7
 - RCBUS40 RS2 = RCBUS40r3jz7
 - RCBUS40 RT4 = RCBUS40r3ipz2
 - RCBUS40 RS4 = RCBUS40r3ip2z2


## Notes

 - GOL RT2/RS2 could remove a via from C10 to U2 GND, but then unconnected - DONE!
   - -1 via to U5 GND from U2 GND
   - Can use same trick on Squires RT2/RS2??? Nope!, there is no via on Squire RS2/RT2
 - Squires has more vias than GOL... why???  TODO: Check




## Template (DO NOT USE!!!)

```none
|Board      | Vias |
|-----------|------|
|Squires RT2| VIA  | 
|Squires RS2| VIA  | 
|Squires RT4| OK   | 
|Squires RS4| OK   | 
|MJ/GOL RT2 | VIA  | 
|MJ/GOL RS2 | VIA  |
|MJ/GOL RT4 | VIA  | 
|MJ/GOL RS4 | VIA  | 
|RCBUS80 RT2| OK   | 
|RCBUS80 RS2| OK   | 
|RCBUS80 RT4| VIA  | 
|RCBUS80 RS4| VIA  | 
|RCBUS40 RT2| OK   | 
|RCBUS40 RS2| OK   | 
|RCBUS40 RT4| OK   | 
|RCBUS40 RS4| OK   | 
```