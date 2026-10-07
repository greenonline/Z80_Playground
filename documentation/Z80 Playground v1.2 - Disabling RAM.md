# Z80 Playground v1.2 - Disabling RAM

## Preamble

Would Z80 Playground support RomWBW, or rather, does RomWBW support the Z80 Playground and the USB reader? 

There would be a need to disable the on-board 64 kB, and use an external board with 512 kB on it.

## Links

 - meh


## Videos

 - meh

## Notes

 - Add ability to disable ROM and ROM on board, so that an external 512 kB can be used.
   - Yet another variant: S/F (**S**witched, **F**ixed)
     - Add jumper to disable RAM, to VCC on CE
     - ROM is already jumpered, up with the two three pin jumpers. add a new jumper.
   - Only for RCBUS80 and RCBUS40, as Squires Bus has no boards.
   - Make Pro version have 512K ROM and RAM


Not easy, due to glue logic – certainly not as easy as just adding a jumper to 5V. May require additional 74xx IC in order to chnge the logic. 

Although... maybe just add the remaining OR gate, after U6A OR,

[![Original RAM select logic][1]][1]

with one input (`RAMEN`) jumpered to 5V to disable RAM, and jumpered to GND to enable RAM. Like so,

[![Disabling RAM logic][2]][2]

Alternatively, disabling the RAM could be done by jumpering both inputs to U8C to GND, or to /WANTROM to enable – thereby saving on the additional OR gate (U6C).

[![Disabling RAM logic more simpler][3]][3]

<!-- Images -->

  [1]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20RAM%20select.png "Original RAM select logic"
  [2]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20RAM%20Disable.png "Disabling RAM logic"
  [3]: ../xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20RAM%20Disable%20Simple.png "Disabling RAM logic more simpler"

