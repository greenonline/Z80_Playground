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


  [1]: ../xtras/hardware/screenshots/v1.2/ebay/Z80%20Playground%20v1.2%20PCB%20and%20components.jpeg "PCB v1.2"
  [2]: ../xtras/hardware/screenshots/v1.2/ebay/Z80%20Playground%20v1.2%20PCB%20(blurry).jpg "PCB v1.2 blurry"

### Deviations from original

 - P1 and P2 renamed J1 and J2, as they are jumpers
 - X1 and X2 renamed Y1 and Y2, as KiCAD auto named



