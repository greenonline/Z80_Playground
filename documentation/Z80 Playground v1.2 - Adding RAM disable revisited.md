# Z80 Playground v1.2 - Adding RAM disable revisited

## Preamble

Suitable for RCBUS40 and RCBUS80, where there is the possibility of using an external memory board with 512 kB ROM and 512 kB RAM for RomWBW.

This is probably one of the last major functionality additions, as there are no more logic gates remaining.

As noted in [Z80 Playground v1.2 - Adding RAM disable](Z80%20Playground%20v1.2%20-%20Adding%20RAM%20disable,md), there is a better method to achieve this disabling, without the use of an addition logic gate, but instead a 3 pin jumper to /WANT_ROM or GND to both inputs of the NOR U8C, see [Z80 Playground v1.2 - Disabling RAM.md](Z80%20Playground%20-%20Disabling%20RAM.md)

[![Disabling RAM logic - simpler][3]][3]

## Notes

RCBUS80 boards are derived from CUN variants, resulting in the new CUNS variants

As the CUN does not exist on RCBUS40, there is no need as NMI is not routed to the bus, then the RAM disable functionality is derived from CUP variants, giving CUPS variants

For RCBUS80, it is better to derive from CUNF, as has 2 less vias than CUN (61 vs. 63), i.e. RT2CUN (RCBUS80r5fz9bo) has 63

## Revisions

### RCBUS80 - starting from fresh (again)

Z80_Playground (RCBUS80 RT4CUNF) - RCBUS80r5cp2fixed3zbo - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

fix: RCBUS80r5cp2fixed3zbo3 (RT4CUNS)

Add J4 1x03 header
Change U8C as /RAMEN gate

Routing easy, J4 placed next to U5 - minimal disruption, no long traces, no new vias.

Update: Rotated J4 180° to consistantly match the 2 layer


Z80_Playground (RCBUS80 RS4CUNF) - RCBUS80r5cp2fixed4zbm - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

fix: RCBUS80r5cp2fixed4zbm3 RS4CUNS

Add J4 1x03 header
Change U8C as /RAMEN gate

Seemed even easier than RT4. J4 next to U5. No long traces, no additional vias.

Update: Rotated J4 180° to consistantly match the 2 layer


Z80_Playground (RCBUS80 RS2CUNF) - RCBUS80r5gz9bp - 61v - DRC_OK (CTS) (JMP)

fix: RCBUS80r5gz9bp3 RS2CUNS

Add J4 1x03 header
Change U8C as /RAMEN gate

Not much room next to U5 for the siting of J4.

Need a via to route WANT_ROM -> No!

Rotate J4 180° works easy

Should the RS4 J4 also be rotated for consistency? DONE!


Z80_Playground (RCBUS80 RT2CUNF) - RCBUS80r5fz9bp - 61v - DRC_OK (CTS) (JMP)

fix: RCBUS80r5fz9bp3

Add J4 1x03 header
Change U8C as /RAMEN gate

Not much room next to U5 for the siting of J4.
Rotate J4 180° works easy

Should the RT4 J4 also be rotated for consistency? DONE!


### RCBUS80 - starting from CUNS

meh


### RCBUS40 - starting from fresh (again)

Z80_Playground (RCBUS40 RT4CUPF) - (RCBUS40r3ipz2b) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ipz2b3 (RT4CUPS)

Add J4 1x03 header
Change U8C as /RAMEN gate

Not much room next to U5 for the siting of J4.

Rotated 180°. Easy.

Z80_Playground (RCBUS40 RS4CUPF) - (RCBUS40r3ip2z2b) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ip2z2b3

Not much room next to U5 for the siting of J4.

Rotated 180°. Easy.

Z80_Playground (RCBUS40 RT2CUPF) - (RCBUS40r3iz7b) - 54v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3iz7b3

Not much room next to U5 for the siting of J4.

Rotated 180°. Easy.

Reduced by -1 via 54 -1 = 53

Z80_Playground (RCBUS40 RS2CUPF) -  (RCBUS40r3jz7b) - 54v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3jz7b3

Not much room next to U5 for the siting of J4.

Rotated 180°. Easy.

Reduced by -1 via 54 -1 = 53



## Conclusion

All done (again)! Thankfully just a couple of boards had to be done. It is unlikely that anymore changes can be done, or features added as the boards are getting pretty full now. 

I am surprised that I've managed to cram in: CTS; Power jumper; Negative-edge triggered NMI, and; this RAM disable upgrade.

Even though the negative edge trigger added an excessive amount of vias to the RS2 and RT2 variants of the RCBUS80 board, seeing as this RAM disable fix did not any any additional vias, the two combined fixes should be taken as a win.

Two remaining changes that would be nice to have are:

 - Disable USB
 - Disable UART

These modifications will be built upon the switched RAM (S) variants created herein this document.


<!-- Images -->

  [3]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20RAM%20Disable%20Simple.png "Disabling RAM logic - simpler"
