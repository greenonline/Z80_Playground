# Z80 Playground v1.2 - layout 

## Preamble

The Z80 Playground v1.2 layout, as derived from the images shown in the video, [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them](https://www.youtube.com/watch?v=MaolTlk7XKM).

## Notes

### Basic block diagram layout

Showing the location of various components, but with few part numbers:

```none
disk            user1 halt /rom
  |               |   |    |
  v               v   v    v
|------------------------------------------|
|    P2 P1    J6 LED LED LED 7414  C  XTAL |
|LED           "   R   R   R    "  C   "   |
|R             "                   R       |
|  J5  R C C R        TTLSerial            |
|C UART           R           R R R   XTAL |
|  "              C+  LEDpwr  R   C    "   |  <- Power
| C                               C        |
|EEPROM          Button Button Button      |
|  "           C  RAM                      |
|                                          |
|                                          |
|C 74HC32  R    CPU              7432 C    |
|          C     "                         |
|C 74HC02  R     "                 "       |
|                                          |
|            Edge connector                |
|------------------------------------------|
```

NOTE: The LED purpose is indicated from *outside* the PCB surrounds

28 pin ZIF for EEPROM???

### Detailed block diagram layout

A larger version of the diagram, showing the components ID, thereby allowing for easier/better placement:

```none
disk             user1 halt /rom
  |                |    |    |
  v                v    v    v
|-----------------------------------------------|
|                                 C7            |
|     J2 J1    J6 LED4 LED6 LED1 7414  C5  XTAL |
|LED2           "  R10  R1   R2    "   C6  CPU  |
|R3             "                 U7   R14      |
|  J5  R8 C1 C2 R15        TTLSerial            |
|C11 U11_UART       R16         R13 R5 R6  XTAL |
|       "           C8  LED3    R7   C17   UART |  <- Power
|C3                                  C18        |
|U3_EEPROM ZIF    SW1  SW3  SW2                 |
|  "              Rst /INT /NMI                 |
|  "           C12  U2_RAM                      |
|                                               |
|                                               |
|C13 74HC32  R4     U1_CPU           7432 C10   |
|     U6     C9       "                U5       |
|C4  74HC02  R9       "                 "       |
|     U8                                        |
|            Edge connector                     |
|-----------------------------------------------|

TTL Serial: TX RX VCC RTS GNS
```

Note: C14, C15 and C16 are missing from layout – they are missing from schematic as well.

#### Images used to see component IDs

##### YouTube

In order to identify the components of the board, I took a couple of series of screenshots from a couple of videos.

First screenshots were of a populated board, taken from:

   - [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them](https://www.youtube.com/watch?v=MaolTlk7XKM&pp=0gcJCcQLAYcqIYzv)

The second series are much clearer screenshots, as it shows an unpopulated board, taken from:

   - [How to make a Z80 Playground from a kit](https://www.youtube.com/watch?v=t-Bo6TdpKzw)
   
 These screenshots can be seen here, [v.1.2](../xtras/hardware/screenshots/v1.2)
 
##### eBay

I managed to find some sold-out items on eBay in Canada, from whence I save the photos of the PCB and components. From [Z80 Playground Single Board Computer Kit](https://www.cafr.ebay.ca/itm/114754711447) (£41.00, C$77.10):

[![PCB v1.2][1]][1]
 
[![PCB v1.2 blurry][2]][2]

### Deviations from original

 - P1 and P2 renamed J1 and J2, as they are jumpers
 - X1 and X2 renamed Y1 and Y2, as KiCAD auto named

### Spacing of the CH376S connectors

The correct physical orientation, spacing and alignment of the two header pin sockets, J5 (02x03) and J6 (02x08), to the CH376S PCB is *essential*. Mostly in their *relative position to eachother* but also, to a lesser extent, the *absolute position on the board*, such that the daughter board does not protrude. The latter part also goes for the TTL serial daughter board.

J5:

 - From top: 
 - From left: 

J6:

 - From top: 
 - From left: 

J5 to J6:

 - Horizontal: 
 - Vertical: 

Note that the shorted Rx and GND pins on J5 are on the side of the 2x3 socket *towards the inside* of the daughter board:

[![CH375S showing jumper on J5][3]][3]

It will be difficult to guesstimate the measurements, without having a physical CH376S module to measure.

### Routing

The routing proved tricker than I expected, mostly as I had preumed that there was an autoroute feature in KiCAD 6 – I was mistaken. Even PCB design software bck in the 80's had autoroute, so gawd knows why KiCAD 6 doesn't!

These four screenshots, showing the traces, were taken to use to replicate the routing:

[![Z80 Playground v1.2 - PCB front#1][4]][4]

[![Z80 Playground v1.2 - PCB front#2][5]][5]

[![Z80 Playground v1.2 - PCB front#3][6]][6]

[![Z80 Playground v1.2 - PCB rear#1][7]][7]

<!-- Images -->

  [1]: ../xtras/hardware/screenshots/v1.2/ebay/Z80%20Playground%20v1.2%20PCB%20and%20components.jpeg "PCB v1.2"
  [2]: ../xtras/hardware/screenshots/v1.2/ebay/Z80%20Playground%20v1.2%20PCB%20(blurry).jpg "PCB v1.2 blurry"
  [3]: ../xtras/hardware/screenshots/CH375S/CH375S%20showing%20jumper%20on%20J5.png "CH375S showing jumper on J5"
  [4]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_1.png "Z80 Playground v1.2 - PCB front#1"
  [5]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_2.png "Z80 Playground v1.2 - PCB front#2"
  [6]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20front_3.png "Z80 Playground v1.2 - PCB front#3"
  [7]: ../xtras/hardware/screenshots/v1.2/unpopulated/Z80%20Playground%20v1.2%20-%20PCB%20rear_1.png "Z80 Playground v1.2 - PCB rear#1"


