# Z80 Playground v1.2 - Addressing

## Preamble

In order to accommodate a number of external boards and IO, then better address decoding is required – so as to not require the removal of the CH375 and prising the UART out of the socket. 

The simplistic address decoding used on the Z80 Playground has repeating IO devices every 8 (UART) and 16 (USB) IO addresses.

Having jumpers for, at least, 4 address pins (or 4 DIP switches) to select HIGH or LOW for A4-A7 (via switchable NOT), would be desirable.

The ability to disable the USB and UART should also be incorporated.

## Links

## Notes

### PIO

For a method that offers a DIP switch selectable address.

From [SC103 – Z80 PIO module (RC2014)](https://smallcomputercentral.com/rcbus/sc100-series/sc103-z80-pio-module-rc2014/#user-guide), and the [schematic](https://smallcomputercentral.com/wp-content/uploads/2019/03/sc103-v1-0-pio-schematic.jpg?w=768&h=542)

[![Z80 PIO schematic][1]][1]

The decoding is done by a 74HCT688, like so

[![Addressing using 74HCT688][20]][20]

Note: A0 and A1 go direct to PIO

Note: IEI and IEO are jumpered to RCBUS38 and RCBUS39

### SIO/CTC

From [SC110 – Z80 Serial (RC2014)](https://smallcomputercentral.com/rcbus/sc100-series/sc110-z80-serial-rc2014-3/), the [schematic](https://smallcomputercentral.com/wp-content/uploads/2018/10/sc110-v1-1-sio2ctc-schematic.pdf)

[![Z80 SIO/CTC schematic][21]][21]

The decoding for the two ICs is done using a 74HCT138, like so

[![Addressing using 74HCT138][22]][22]

SIO: 0x20
CTC: 0x24

Note that the address(es) can not be changed – unless the outputs of the 74138 are changed. The outputs should be jumpered at the very least, so as to offer *some* variability in the addressing, as per SMB decoding, below.

### SMB

The SIO/CTC address decoding is *similar* to, but not the same as, the SMB address decoding for the paging of the RomWBW, which uses a 74HCT138 3 to 8 line decoder. SMB uses A4-A7, IORQ and M1. The selection of the address is made via a jumper selecting one of the outputs of the 74HCT138.

From [Z80 retrocomputing 15 - CP/M on RC2014 Revisited, Using RomWBW](https://www.youtube.com/watch?v=pxZC2J-aeu0):

[![Addressing using 74HCT138 - SMB paging][23]][23]


<!-- Images -->

  [1]: https://smallcomputercentral.com/wp-content/uploads/2019/03/sc103-v1-0-pio-schematic.jpg?w=768&h=542
  [20]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20Addressing_74HCT688.png "Addressing using 74HCT688"
  [21]: ../xtras/hardware/screenshots/RomWBW_compatibility/sc110-v1-1-sio2ctc-schematic.png "Z80 SIO/CTC schematic"
  [22]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20Addressing_74HCT138.png "Addressing using 74HCT138"
  [23]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20Addressing_74HCT138_SMB_Page.png "Addressing using 74HCT138 - SMB paging"


