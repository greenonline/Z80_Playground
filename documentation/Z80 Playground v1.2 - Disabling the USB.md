# Z80 Playground v1.2 - Disabling the USB

## Preamble

This is another simple modification, if the routing allows, where a jumper (J9) is placed between A4 and U8D, giving the option of grounding the input to the NOR gate.

[![Disable USB][6]][6]


## Links

## Notes

### Modifications

#### RCBUS80

Z80_Playground (RCBUS80 RT4CUNSS) - RCBUS80r5cp2fixed3zbo3u - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix: RCBUS80r5cp2fixed3zbo3us (CUNSSS)

Added J9, change input to U8D.

Not too easy, but doble. No extra vias.

Z80_Playground (RCBUS80 RS4CUNSS) - RCBUS80r5cp2fixed4zbm3u - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix: RCBUS80r5cp2fixed4zbm3us (CUNSSS)

Not too easy, but seemed easier second time round, but doble. No extra vias.


Z80_Playground (RCBUS80 RT2CUNSS) - RCBUS80r5fz9bp3u - 63v - DRC_OK (CTS) (JMP)

Fix: RCBUS80r5fz9bp3us (CUNSSS)

Not easy.

+1 via for A4

+1 via for USBEN

63 + 2 = 65 vias

Z80_Playground (RCBUS80 RS2CUNSS) - RCBUS80r5gz9bp3u - 63v - DRC_OK (CTS) (JMP)

Fix: RCBUS80r5gz9bp3u (CUNSSS)

Not easy.

+1 via for A4

+1 via for USBEN

63 + 2 = 65 vias

#### RCBUS40

Z80_Playground (RCBUS40 RT4CUPSSF) - (RCBUS40r3ipz2b3u) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ipz2b3us (CUPSSS)

Not easy, but done, no extra vias.

Z80_Playground (RCBUS40 RS4CUPSSF) - (RCBUS40r3ip2z2b3u) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ip2z2b3us (CUPSSS)

Not easy, but done, no extra vias.


Z80_Playground (RCBUS40 RT2CUPSSF) - (RCBUS40r3iz7b3u) - 55v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3iz7b3u (CUPSSS)

A4 routed without needing a via!

+1 via for USBEN

55 + 1 = 56



Z80_Playground (RCBUS40 RS2CUPSSF) -  (RCBUS40r3jz7b3u) - 55v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3jz7b3us (CUPSSS)

A4 routed without needing a via!

+1 via for USBEN

55 + 1 = 56



## Conclusion

If the cost of adding the ability to disable the USB to the 2-layer boards is an additional two vias then it is a price worth paying for the added flexibility/varsatility.

<!-- Images -->

  [6]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20USB%20Disable.png "Disabling USB logic"
