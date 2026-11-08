# Z80 Playground v1.2 - Disabling the UART

## Preamble

This is a simple enough modification, routing allowing, which consists of just a jumper (J5) in between A3 and CS0, giving the option of grounding the CS0 input to the UART.

Disabling the UART takes priority (in terms of implementation order) over disabling the USB as the IC is slighty more difficult to prise out that just removing the CH375 board.

## Links

## Notes

### Modifications

#### RCBUS80

Z80_Playground (RCBUS80 RT4CUNS) - RCBUS80r5cp2fixed3zbo3 - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix: RCBUS80r5cp2fixed3zbo3u (RT4CUNSS)

Add jumper J5 between A3 and CS0 in UART

Not much space, difficult to route `UARTEN`

Turn 90°, not so easy, but doable. No extra vias. A few GND links.



Z80_Playground (RCBUS80 RS4CUNS) - RCBUS80r5cp2fixed4zbm3 - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix: RCBUS80r5cp2fixed4zbm3u (CUNSS)

Add jumper J5 between A3 and CS0 in UART

Seemed easier than the RT4 above.

Z80_Playground (RCBUS80 RT2CUNS) - RCBUS80r5fz9bp3 - 61v - DRC_OK (CTS) (JMP)

Fix: RCBUS80r5fz9bp3u (CUNSS)

Not much space, quite difficult, and need to move vias.

+1 via to UARTEN

+1 via to A3

61 + 2 = 63 vias

Z80_Playground (RCBUS80 RS2CUNS) - RCBUS80r5gz9bp3 - 61v - DRC_OK (CTS) (JMP)

Fix: RCBUS80r5gz9bp3u (CUNSS)

+1 via to UARTEN

+1 via to A3

61 + 2 = 63 vias

#### RCBUS40

Note: NO CUNS variant exists for RCBUS40, as the NMI is not routed to the bus pins.

Z80_Playground (RCBUS40 RT4CUPS) - (RCBUS40r3ipz2b3) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ipz2b3u (CUPSSF)

Not too difficult, no extra vias needed.

Z80_Playground (RCBUS40 RS4CUPSFF) - (RCBUS40r3ip2z2b3) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ip2z2b3u (CUPSSF)

Not too difficult, no extra vias needed.

Z80_Playground (RCBUS40 RT2CUPSFF) - (RCBUS40r3iz7b3) - 53v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3iz7b3u (CUPSSF)

Not easy.

+1 via for UARTEN

+1 via for A3

53 + 2 = 55 vias

Z80_Playground (RCBUS40 RS2CUPSFF) -  (RCBUS40r3jz7b3) - 53v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3jz7b3u (CUPSSF)

Not easy.

+1 via for UARTEN

+1 via for A3

53 + 2 = 55 vias



## Conclusion

If the cost of adding the ability to disable the UART to the 2-layer boards is an additional two vias then it is a price worth paying for the added flexibility/varsatility.
