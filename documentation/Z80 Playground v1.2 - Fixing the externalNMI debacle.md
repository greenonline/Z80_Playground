# Z80 Playground v1.2 - Fixing the externalNMI debacle

## Preamble

Afte rhaving discovered right at the end of the PCB design process that I had an error in the schematic for (nearly) *all* of the boards, where the NMI line on the bus was not connected to the positive edge triggered `externalNMI`, or `EXT_NMI`, signal.

RCBUS40 boards were not affected as NMI is not routed to the bus.

In the case of the Squires and MJ/GOL boards the fix ws relatively simple. On RCBUS80 boards, not so.

## Random note

Z80_Playground (RCBUS80 RT2NP) - RCBUS80r5fz9 - 53v - DRC_OK

The front bus silk screen can, and should, be moved four places to the right, in order to align with the pins more correctly. Need to ungroup from the rear silkscreen first. Then regroup once front has been moved 4 clicks to the right.

But then the bottom row looks a bit bad, in places

Moving right by five clicks caued an additional silkscreen warning.

Check for other variants and subvariants.



==============

## Notes

### Fixability for externalNMI

Note: 4 layer required a trace to NMI, 2 layer did not
Note: For some reason 4 layer were more difficult to fix than the 2 layer.
Note: CUN variant not touched, no point.

#### Squires

Z80_Playground (Squires RS4CP) - aligned4b2pcz3a - 20v -DRC_OK (CTS)

easy to fix

Z80_Playground (Squires RT2NP) - aligned4b4z8 - 54v - DRC_OK

easy to fix -> aligned4b4z8n

Z80_Playground (Squires RT2NU) - aligned4b4z8j - 54v - DRC_OK (JMP)

easy to fix -> aligned4b4z8jn

Z80_Playground (Squires RT2CUP) - aligned4b4z8b - 55v - DRC_OK (CTS) (JMP)

easy to fix -> aligned4b4z8bn

Z80_Playground (Squires RT2CP) - aligned4b4z8a - 55v - DRC_OK (CTS)

easy to fix -> aligned4b4z8an

Z80_Playground (Squires RT4CP) - aligned4b2paz3a - 20v - DRC_OK (CTS)

easy to fix -> aligned4b2paz3an

Z80_Playground (Squires RT4CUP) - aligned4b2paz3b - 20v - DRC_OK (CTS) (JMP)

easy to fix -> aligned4b2paz3bn

Z80_Playground (Squires RT4NP) - aligned4b2paz3 - 20v - DRC_OK

easy to fix -> aligned4b2paz3n

Z80_Playground (Squires RT4NU) - aligned4b2paz3j - 20v - DRC_OK (JMP)

easy to fix -> aligned4b2paz3jn

Z80_Playground (Squires RS2CP) - aligned4b6z8a - 54v - DRC_OK (CTS)

easy to fix -> aligned4b6z8an

Z80_Playground (Squires RS2CUP) - aligned4b6z8b - 54v - DRC_OK (CTS) (JMP)

easy to fix -> aligned4b6z8bn

Z80_Playground (Squires RS2NP) - aligned4b6z8 - 54v - DRC_OK

easy to fix -> aligned4b6z8n

Z80_Playground (Squires RS2NU) - aligned4b6z8j - 54v - DRC_OK (JMP)

easy to fix -> aligned4b6z8jn

Z80_Playground (Squires RS4CP) - aligned4b2pcz3a - 20v -DRC_OK (CTS)

easy to fix -> aligned4b2pcz3an

Z80_Playground (Squires RS4CUP) - aligned4b2pcz3b - 20v - DRC_OK (CTS) (JMP)

easy to fix -> aligned4b2pcz3bn

Z80_Playground (Squires RS4NP) - aligned4b2pcz3 20v - DRC_OK

easy to fix -> aligned4b2pcz3n

Z80_Playground (Squires RS4NU) - aligned4b2pcz3j 20v - DRC_OK (JMP)

easy to fix -> aligned4b2pcz3jn


#### MJ/GOL_

Z80_Playground (MJ/GOL RT2CUP) - alignedcz4b - 49v - DRC_OK (CTS) (JMP)

easy to fix -> alignedcz4bn

Z80_Playground (MJ/GOL RT2CP) - alignedcz4a - 49v - DRC_OK (CTS)

easy to fix -> alignedcz4an

Z80_Playground (MJ/GOL RT2NP) - alignedcz4 - 48v - DRC_OK

easy to fix -> alignedcz4n

Z80_Playground (MJ/GOL RT2NU) - alignedcz4j - 48v - DRC_OK (JMP)

easy to fix -> alignedcz4jn

Z80_Playground (MJ/GOL RT4CP) - aligned2pc2za - 22v - DRC_OK (CTS)

not so easy to fix -> aligned2pc2zan, 21v
Removed via to BUSACK bus pin


Z80_Playground (MJ/GOL RT4CUP) - aligned2pc2zb - 22v - DRC_OK (CTS) (JMP)
not so easy to fix -> aligned2pc2zbn, 21v
Removed via to BUSACK bus pin

Z80_Playground (MJ/GOL RT4NP) - aligned2pc2z - 22v - DRC_OK
not so easy to fix -> aligned2pc2zn, 21v
Removed via to BUSACK bus pin


Z80_Playground (MJ/GOL RT4NU) - aligned2pc2zj - 22v - DRC_OK (JMP)
not so easy to fix -> aligned2pc2zjn, 21v
Removed via to BUSACK bus pin


Z80_Playground (MJ/GOL RS2CP) - alignedez4a - 49v - DRC_OK (CTS)
easy to fix -> alignedez4an


Z80_Playground (MJ/GOL RS2CUP) - alignedez4b - 49v - DRC_OK (CTS) (JMP)
easy to fix -> alignedez4bn

Z80_Playground (MJ/GOL RS2NP) - alignedez4 - 48v - DRC_OK
easy to fix -> alignedez4n

Z80_Playground (MJ/GOL RS2NU) - alignedez4j - 48v - DRC_OK (JMP)
easy to fix -> alignedez4jn


Z80_Playground (MJ/GOL RS4CP) - aligned2pc3za - 22v - DRC_OK (CTS)
not so easy to fix -> aligned2pc3zan, 21v
Removed via to BUSACK bus pin

Z80_Playground (MJ/GOL RS4CUP) - aligned2pc3zb - 22v - DRC_OK (CTS) (JMP)
not so easy to fix -> aligned2pc3zbn, 21v
Removed via to BUSACK bus pin

Z80_Playground (MJ/GOL RS4NP) - aligned2pc3z - 22v - DRC_OK
not so easy to fix -> aligned2pc3zn, 21v
Removed via to BUSACK bus pin


Z80_Playground (MJ/GOL RS4NU) - aligned2pc3zj - 22v - DRC_OK (JMP)
not so easy to fix -> aligned2pc3zjn, 21v
Removed via to BUSACK bus pin

#### RCBUS40

Z80_Playground (RCBUS40 RT2CP) - (RCBUS40r3iz7a) - 54v - DRC_OK (CTS)
easy to fix -> RCBUS40r3iz7an (not needed)
NMI is not on bus, but still need to tidy the address lines' labels
Why is TX, Rx, IEI nd IEO not connected?

#### RCBUS80

Z80_Playground (RCBUS80 RT2CP) - RCBUS80r5fz9a- 54v - DRC_OK (CTS)

not easy to fix -> RCBUS80r5fz9an +2v = 56v

Z80_Playground (RCBUS80 RT2CUP) - RCBUS80r5fz9b- 54v - DRC_OK (CTS) (JMP)

not easy to fix -> RCBUS80r5fz9bn +2v = 56v

Z80_Playground (RCBUS80 RT2NP) - RCBUS80r5fz9 - 53v - DRC_OK

not easy to fix -> RCBUS80r5fz9n +2v = 55v

Z80_Playground (RCBUS80 RT2NU) - RCBUS80r5fz9j - 53v - DRC_OK (JMP)

not easy to fix -> RCBUS80r5fz9jn +2v = 55v

Z80_Playground (RCBUS80 RT4CPP) - RCBUS80r5cp2fixed3za - 25>24v - HL5_FIXED, DRC_OK (CTS)

easy to fix -> RCBUS80r5cp2fixed3zan

Z80_Playground (RCBUS80 RT4CUP) - RCBUS80r5cp2fixed3zb - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

easy to fix -> RCBUS80r5cp2fixed3zbn

Z80_Playground (RCBUS80 RT4NPP) - RCBUS80r5cp2fixed3z - 25>24v - HL5_FIXED, DRC_OK

easy to fix -> RCBUS80r5cp2fixed3zn

Z80_Playground (RCBUS80 RT4NUP) - RCBUS80r5cp2fixed3zj - 25>24v - HL5_FIXED, DRC_OK (JMP)

easy to fix -> RCBUS80r5cp2fixed3zjn

Z80_Playground (RCBUS80 RS2CP) - RCBUS80r5gz9a - 54v - DRC_OK (CTS)

not easy to fix -> RCBUS80r5gz9an +2v = 56v

Z80_Playground (RCBUS80 RS2CUP) - RCBUS80r5gz9b - 54v - DRC_OK (CTS) (JMP)

not easy to fix -> RCBUS80r5gz9bn +2v = 56v

Z80_Playground (RCBUS80 RS2NP) - RCBUS80r5gz9 - 53v - DRC_OK

not easy to fix -> RCBUS80r5gz9n +2v = 55v

Z80_Playground (RCBUS80 RS2NU) - RCBUS80r5gz9j - 53v - DRC_OK (JMP)

not easy to fix -> RCBUS80r5gz9jn +2v = 55v

Z80_Playground (RCBUS80 RS4CPP) - RCBUS80r5cp2fixed4za - 25>24v - HL5_FIXED, DRC_OK (CTS)

easy to fix -> RCBUS80r5cp2fixed4zan

Z80_Playground (RCBUS80 RS4CUP) - RCBUS80r5cp2fixed4zb - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

easy to fix -> RCBUS80r5cp2fixed4zbn

Z80_Playground (RCBUS80 RS4NPP) - RCBUS80r5cp2fixed4z - 25>24v - HL5_FIXED, DRC_OK

easy to fix -> RCBUS80r5cp2fixed4zn

Z80_Playground (RCBUS80 RS4NUP) - RCBUS80r5cp2fixed4zj - 25>24v - HL5_FIXED, DRC_OK (JMP)

easy to fix -> RCBUS80r5cp2fixed4zjn


### Subvariants


 - RS2CPP
 - RS2CUN (*)
 - RS2CUP (*)
 - RS2NPP
 - RS2NUP

 - RS4CPP
 - RS4CUN (*)
 - RS4CUP (*)
 - RS4NPP
 - RS4NUP

 - RT2CPP
 - RT2CUN (*)
 - RT2CUP (*)
 - RT2NPP
 - RT2NUP

 - RT4CPP
 - RT4CUN (*)
 - RT4CUP (*)
 - RT4NPP
 - RT4NUP


Note that there is no:

 - CPN
 - NPN
 - NUN


