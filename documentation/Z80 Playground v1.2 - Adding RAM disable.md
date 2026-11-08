# Z80 Playground v1.2 - Adding RAM disable

## Preamble

Suitable for RCBUS40 and RCBUS80, where there is the possibility of using an external memory board with 512 kB ROM and 512 kB RAM for RomWBW.

This is probably one of the last major functionality additions, as there are no more logic gates remaining.

## Notes

RCBUS80 boards are derived from CUN variants, resulting in the new CUNS variants

As the CUN does not exist on RCBUS40, there is no need as NMI is not routed to the bus, then the RAM disable functionality is derived from CUP variants, giving CUPS variants

## Revisions

### RCBUS80

Z80_Playground (RCBUS80 RT4CUN) - RCBUS80r5cp2fixed3zbo - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

fix: RCBUS80r5cp2fixed3zbo2 (RT4CUNS)


Add J4 1x03 header
Add U6C as /RAMEN gate
Moved Disk LED and shifted jumpers
Relatively painless addition, no additional vias required


Z80_Playground (RCBUS80 RS4CUN) - RCBUS80r5cp2fixed4zbm - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

fix: RCBUS80r5cp2fixed4zbm2 RS4CUNS

Add J4 1x03 header
Add U6C as /RAMEN gate
Moved Disk LED and shifted jumpers
Relatively painless addition, no additional vias required



Z80_Playground (RCBUS80 RS2CUN) - RCBUS80r5gz9bp - 61v - DRC_OK (CTS) (JMP)

Fix: RCBUS80r5gz9bp2 (RS2CUNS)

Add J4 1x03 header
Add U6C as /RAMEN gate
Moved Disk LED and shifted jumpers
Relatively painless addition, no additional vias required



Z80_Playground (RCBUS80 RT2CUN) - RCBUS80r5fz9bp - 61v - DRC_OK (CTS) (JMP)

Fix: RCBUS80r5fz9bp2 (RT2CUNS)

Add J4 1x03 header
Add U6C as /RAMEN gate
Moved Disk LED and shifted jumpers
Relatively painless addition, no additional vias required

### RCBUS40

Z80_Playground (RCBUS40 RT4CUP) - (RCBUS40r3ipz2b) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ipz2b2 (RT4CUPS)

Add J4 1x03 header
Add U6C as /RAMEN gate
Moved Disk LED and shifted jumpers
Relatively painless addition, no additional vias required


Z80_Playground (RCBUS40 RS4CUP) - (RCBUS40r3ip2z2b) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ip2z2b2 (RS4CUPS)

Add J4 1x03 header
Add U6C as /RAMEN gate
Moved Disk LED and shifted jumpers
Relatively painless addition, no additional vias required


Z80_Playground (RCBUS40 RT2CUP) - (RCBUS40r3iz7b) - 54v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3iz7b2 (RT2CUPS)

Horrible long circuitous trace on /RAM_EN, difficult to connect to. This is much more difficult than the RCBUS80 variant. 

Managed it, without any vias, but more circuitous traces added.

Z80_Playground (RCBUS40 RS2CUP) -  (RCBUS40r3jz7b) - 54v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3jz7b2 (RS2CUPS)

Horrible long circuitous trace on /RAM_EN, difficult to connect to. This is much more difficult than the RCBUS80 variant. TODO: Finish

Managed it, without any vias, but more circuitous traces added.


## Conclusion

All done! Thankfully just a couple of boards had to be done. It is unlikely that anymore changes can be done, or features added as the boards are getting pretty full now. 

I am surprised that I've managed to cram in: CTS; Power jumper; Negative-edge triggered NMI, and; this RAM disable upgrade.

Even though the negative edge trigger added an excessive amount of vias to the RS2 and RT2 variants of the RCBUS80 board, seeing as this RAM disable fix did not any any additional vias, the two combined fixes should be taken as a win.

## Change

There is an alternative method, which does not require the use of an additional gate, but instead a 3 pin jumper to /WANT_ROM or GND to both inputs of the NOR U8C, see [Z80 Playground v1.2 - Disabling RAM.md](Z80%20Playground%20-%20Disabling%20RAM.md)

[![Disabling RAM logic - simpler][3]][3]

See [Z80 Playground v1.2 - Adding RAM disable revisited](Z80%20Playground%20v1.2%20-%20Adding%20RAM%20disable%20revisited.md)

<!-- Images -->

  [3]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20RAM%20Disable%20Simple.png "Disabling RAM logic - simpler"
