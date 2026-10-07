# Z80 Playground v1.2 - Running RomWBW

## Preamble

Would Z80 Playground support RomWBW, or rather, does RomWBW support the Z80 Playground and the USB reader? If not, what would it take to make it supported? Is banking required? Is 512 kB required or is that for everything? What is the smallest RomWBW image?

## Links

 - [RomWBW Architecture](https://www.retrobrewcomputers.org/lib/exe/fetch.php?media=software:firmwareos:romwbw:romwbw_architecture.pdf)

## Videos

 - [3 minute demo of stock RC2014 converted to CP/M](https://www.youtube.com/watch?v=Y5o7FQ0vMNY)
 - [Z80 retrocomputing 15 - CP/M on RC2014 Revisited, Using RomWBW](https://www.youtube.com/watch?v=pxZC2J-aeu0)

## Notes

### SMBaker

The minimum requirement is 512 kB ROM and 512 kB RAM, apparently, so as it stands, Z80 Playground is not compatible with RomWBW – something for the Pro version.


Hack the ROM source as per SMB ([video 15](https://www.youtube.com/watch?v=pxZC2J-aeu0) above), and add a `ZPG` build option menu.

Schematic taken from the same video:

[![SMB Schematic for RomWBW][6]][6]

Addresses:

`0x70`, `0x78` - write (74HCT670 x 2)

`0x7C` - Initialise to zero: Page enable flip flop (74HCT74) 

Note from schematic:

> Must disable RomWBW RTC as it would normally inhabit 0x70.

Note that a better schematic is availbble on [RC2014.co.uk](https://8b8bf43264c2f150841a.b-cdn.net/wp-content/uploads/2018/04/512kROMRAM.pdf):

[![Complete SMB schematic for RomWBW][7]][7]

#### ICs

 - 74HCT74
 - 74HCT670 x 2
 - 74HCT138
 - 74HCT139



 - 512 kB RAM : AS6C4008
   - footprint: `Package_DIP:DIP-32_W15.24mm`
 - 512 kB ROM : 39SF040
   - footprint: `Package_DIP:DIP-32_W15.24mm`

### Cousins

Note that there is a different form of the schematic: [smallcomputercentral](https://smallcomputercentral.com/wp-content/uploads/2023/05/sc714_v1.0.0_2023-05-15_22-51_schematic.pdf):

[![SCC schematic for RomWBW][8]][8]


#### ICs

 - 74HCT688
 - 74HCT157
 - 74HCT139
 - 74HCT273

### Queries

 - Can the ROM RAM board work and disable the on-board ROM/RAM? Probably not without a jumper being added to RAM CS. The ROM already has a switch(?).


<!-- Images -->

  [6]: ../xtras/hardware/screenshots/RomWBW_compatibility/Schematic_for_RomWBW.png "SMB Schematic for RomWBW"
  [7]: ../xtras/hardware/screenshots/RomWBW_compatibility/512kROMRAM.png "Complete SMB schematic for RomWBW"
  [8]: ../xtras/hardware/screenshots/RomWBW_compatibility/sc714_v1.0.0_2023-05-15_22-51_schematic.png "SCC schematic for RomWBW"

