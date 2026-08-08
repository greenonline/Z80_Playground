# Z80_Playground
A repo containing info for the Z80 SBC, designed by John Squires

# Z80_Playground

Or [playgroundZ80](https://github.com/greenonline/playgroundZ80)!!!

## Preamble

John Squires, of the now defunt [8bitstack.co.uk](https://8bitstack.co.uk), and the YouTube channel, [John Squires](https://www.youtube.com/@CircuitBreaker256), created a very nifty Z80 SBC, called *Z80 Playground*, that could run CP/M and Tiny BASIC, amongst other things. 

Whilst it is now pretty difficult to find much info out about its design, he did mention that an earlier iteration upon breadboard, was based upon the *Four IC Z80 SBC* – in the videos, he refers to similarity of the breadboard version to the "4 IC Z80" design – which is, most probably, this project, [A 4\$, 4ICs, Z80 homemade computer on breadboard](https://hackaday.io/project/19000-a-4-4ics-z80-homemade-computer-on-breadboard/). 

Unfortunately, around 2022, new videos ceased to be posted, and the whole project seemed to have died.

This is the best image of the PCB and components that I could find, via [a sold out ebay listing](https://www.cafr.ebay.ca/itm/114754711447):

[![PCB v1.2][1]][1]

  [1]: xtras/hardware/screenshots/v1.2/ebay/Z80%20Playground%20v1.2%20PCB%20and%20components.jpeg "PCB v1.2"


There don't appear to be any parts lists, schematics, PCB layouts, Gerber files, etc. – basically, there seems to be little in the way of hardware documentation, apart from the videos. However, there are still Github repos for the software, that are still up, so that is good.

Using the Wayback machine I managed to get hold of some PDFs of the schematic diagrams for v1.1 and v.1.2, and some additional software, see the section **Wayback data** below.

While I couldn't find any PDFs of the v1.0 schematic digram, I did manage to get some screenshots of the v1.0 schematic digram, from a video. See the section **Screenshots** below.

From the schematic diagrams, using KiCAD 6, I managed to recreate the schematics and the PCB, for v1.2.

I reused, where I could, the Squires '*forward-slash-and-lowercase-camelcase*' type of annotation – even though it feels rather inconsistent and messy/awkward.

In addition to the original Squires version, I also made two other variants: 

 - A (IMHO) better annotated version (`GOL`, AKA `MJ`, variant), using a shorter (more standard) '*uppercase-and-underscore*' form of annotation, and; 
 - A version using an RC2014 Extended bus (`RCBUS` variant), that should make the board a bit more useful, *if* you so happen to have an RC2014 lying around – see [playgroundZ80](https://github.com/greenonline/playgroundZ80).

There is also a version arising from my *initial attempt*, that has two styles of annotation: the Squires 'forward-slash-and-lowercase-camelcase' type and a shorter (more standard) 'uppercase-and-underscore' form of annotation. This is the so-called `dual version` variant. I have retained this as a starting point for other variants, but it should not be used as a complete board design.

I have also had to make some changes relating to how KiCAD works, do the resulting schematics will not match exactly.

I also "tidied up" a few errors, inconsistencies, and omissions.

For the PCB, I had to guess what footprints to use, so they may not match the original PCBs, produced by John Squires, exactly. See the section **Footprints used** below.

## See also

 - [playgroundZ80](https://github.com/greenonline/playgroundZ80), an RCBUS (RC2014) variant of the Z80 Playground.

## Links

 - [RC2014](https://rc2014.co.uk/)

From the [Wayback Machine for 8bitstack.co.uk](https://web.archive.org/web/20210000000000*/8bitstack.co.uk):

 - [Schematic v1.1 and v1.2](https://web.archive.org/web/20210106120858/http://8bitstack.co.uk/) from 8/1/2021
 - [More links, z80ccp](https://web.archive.org/web/20210508135102/http://8bitstack.co.uk/)
 - [Even more links, sd.com, z80ccp, core_jump, 2048](https://web.archive.org/web/20211020202250/http://8bitstack.co.uk/)
 - There are many *other* snapshots of the site, present on the Wayback Machine, that I have not investigated, due to time constraints. I only checked the earliest three snapshots or so.
 
### Z80 Playground based projects

 - [A self-contained CP/M computer based on the Z80 Playground](https://kevinboone.me/z80pg.html)
 - [John Squires "Z80 Playground"](https://www.mccrash-racing.co.uk/philg/z80playground/playground.htm)
 - [Building a Z80-MBC3 standalone computer](https://www.digitalplayground.be/?p=6292)

### Manuals

#### German

 - From [Projekte___Z80-Playground](https://erik-bartmann.de/?Projekte___Z80-Playground):
   - [Danke für den Kauf](https://erik-bartmann.de/userfiles/downloads/Z80/Danke%20fuer%20den%20Kauf%20des%20Z80-Playground.pdf), repo copy: [Danke für den Kauf](xtras/manuals/de/Danke%20fuer%20den%20Kauf%20des%20Z80-Playground.pdf) 
   - [Z80-Playground](https://erik-bartmann.de/userfiles/downloads/Z80/Z80Playground.pdf), repo copy: [Z80-Playground](xtras/manuals/de/Z80Playground.pdf)

## Videos

Some links to videos on John Squires' YouTube channel:

 - [CP/M Z80 single board computer, on a solderless breadboard (PART 1)](https://www.youtube.com/watch?v=swvv5-zIv2E&list=PL3arA6T9kycrDQMQRP57nJH84IMWwp1zI) - Playlist
 - Other non-playlist videos by John Squires:
   - [Flow Control for UART Serial communication between Z80 Playground and a PC](https://www.youtube.com/watch?v=RFxSKGnuisE)
   - [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them](https://www.youtube.com/watch?v=MaolTlk7XKM&pp=0gcJCcQLAYcqIYzv)
   - [Upgrade your CCP in CP/M v2.2](https://www.youtube.com/watch?v=mEcQ2FOlLlU)
   - [How to make a Z80 Playground from a kit](https://www.youtube.com/watch?v=t-Bo6TdpKzw)
   - [Z80 Playground February 2021 Update](https://www.youtube.com/watch?v=t4nq6IOgfbk)
   - [Building a Standalone Z80 CP/M Computer (part 1)](https://www.youtube.com/watch?v=zhszathMpgY) - already in playlist
   - [Downloading and using CP/M software on the Z80 Playground](https://www.youtube.com/watch?v=b1sviTM_aTE)
   - [Building a standalone Z80 CP/M computer (part 2)](https://www.youtube.com/watch?v=SngbPltYnUU)
   - [Building a standalone Z80 CP/M computer (part 3)](https://www.youtube.com/watch?v=jwQrlnJohNk)
  - There *may* be others...

## Notes

### Screenshots

Some [screen shots of v.1.0 schematic](xtras/hardware/screenshots/v1.0/) are available.

The screenshots of schematics and PCB layout of the v1.0 board were taken from [Z80 Playground - the Single Board Computer that runs CP/M](https://www.youtube.com/watch?v=CIgxkcXNp1w&list=PL3arA6T9kycrDQMQRP57nJH84IMWwp1zI&index=7) at [4:05](https://www.youtube.com/watch?v=CIgxkcXNp1w&list=PL3arA6T9kycrDQMQRP57nJH84IMWwp1zI&index=7&t=245).

### Wayback data

Information and data recovered from the  [Wayback Machine for 8bitstack.co.uk](https://web.archive.org/web/20210000000000*/8bitstack.co.uk), included in *this* repo:

 - Hardware
   - [V1.1 schematic PDF](xtras/hardware/wayback/Schematic_Z80-playground_v1_1.pdf)
   - [v1.2 schematic PDF](xtras/hardware/wayback/Schematic_Z80-playground_v_1_2.pdf)
 - Software
   - [SD](xtras/software/wayback/Z80Playground_WB_software/SD.zip)
   - [Z80-CCP](xtras/software/wayback/Z80Playground_WB_software/Z80CCP.zip)
   - [core_jump](xtras/software/wayback/Z80Playground_WB_software/core_jump.zip)
   - [2048](xtras/software/wayback/Z80Playground_WB_software/2048.zip)

 
Source links:
 
 - [Schematic v1.1 and v1.2](https://web.archive.org/web/20210106120858/http://8bitstack.co.uk/) from 8/1/2021
 - [More links, z80ccp](https://web.archive.org/web/20210508135102/http://8bitstack.co.uk/)
 - [Even more links, sd.com, z80ccp, core_jump, 2048](https://web.archive.org/web/20211020202250/http://8bitstack.co.uk/)
 
### Footprints used

#### MJ/GOL variant

This was the first PCB layout attempt. The footprints used are listed below.

Capacitors:

 - `C8` 47 µF: `Capacitor_THT:CP_Radial_D6.3mm_P2.50mm`
 - `C9` 100 nF: `Capacitor_THT:C_Disc_D5.1mm_W3.2mm_P5.00mm`
 - `C17` 47 pF: `Capacitor_THT:C_Disc_D3.8mm_W2.6mm_P2.50mm`
 - `C6` 8 pF: `Capacitor_THT:C_Disc_D3.8mm_W2.6mm_P2.50mm`

Resistors:

 - `R8` 10k: `Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal`

XTAL

 - `Y1` :`Crystal:Crystal_HC49-4H_Vertical`

Switch

 - `SW1`: `Button_Switch_SMD:SW_SPST_CK_RS282G05A3`
 - Also posible: `Button_Switch_SMD:SW_Tactile_SPST_NO_Straight_CK_PTS636Sx25SMTRLFS`
 - OMRON: `???`

Headers

 - `H1`, `Connector_PinHeader_2.54mm:PinHeader_1x06_P2.54mm_Horizontal`
 - `H2`, was `My_Components:Conn_Pin_Header_39x1_2.54mm`, now `Connector_PinHeader_2.54mm:PinHeader_1x39_P2.54mm_Horizontal`, 

Jumpwers:

 - `J1`, `Connector_PinHeader_2.54mm:PinHeader_1x03_P2.54mm_Vertical`
 - `J5`, `Connector_PinSocket_2.54mm:PinSocket_2x03_P2.54mm_Vertical`
 - `J6`, `Connector_PinSocket_2.54mm:PinSocket_2x08_P2.54mm_Vertical`

### KiCAD 6 quirks

Not really quirks, but changes, or extra tasks, that I found were required, in order to create the schematic in KiCAD 6.

#### 61512 RAM

I had to create a 61512 RAM IC symbol, within KiCAD, as KiCAD 6 does not natively support it, or provide one.

Available on Github: [61512 for KiCAD 6](https://github.com/greenonline/61512_for_KiCAD_6)

#### 74HC32

As a 74HC32 was not present on KiCAD 6, I had to use a 74LS32 instead – same pinout.

### Layout

Please refer to [Z80 Playground v1.2 - layout](documentation/Z80%20Playground%20v1.2%20-%20layout.md).

## Parts list

Note: This following table is deprecated by the next expanded table down.

| Part    | Qty | Description                            |
|---------|-----|----------------------------------------|
| IC      | 8   | IC        total                        |
| Z80     | 1   | CPU                                    |
| 61512   | 1   | RAM                                    |
| 28C256  | 1   | EEPROM                                 |
| 16C550  | 1   | UART                                   |
| 74HC02  | 1   | NOR                                    |
| 74HC32  | 2   | OR                                     |
| 74HC14  | 1   | NOT                                    |
| Switch  | 3   | Push button                            |
| LED     | 5   | Power, user, halt, rom, disk           |
| R       | 14  | Resistor  total                        |
| 470R    | 1   | Resistor  - CPU clock                  |
| 1k      | 5   | Resistor  - LED                        |
| 1k5     | 1   | Resistor  - UART clock                 |
| 10k     | 6   | Resistor  - Pull down (3), pull up (3) |
| 1M      | 1   | Resistor  - CPU clock                  |
| C       | 13  | Capacitor total                        |
| 8 pF    | 2   | Capacitor - CPU Crystal                |
| 22 pF   | 1   | Capacitor - UART Crytal                |
| 47 pF   | 1   | Capacitor - UART Crytal                |
| 100 nF  | 8   | Capacitor - Decoupling                 |
| 1 µF    | 1   | Capacitor - Interrupt                  |
| 10 µF   | 1   | Capacitor - Reset                      |
| 47 µF   | 1   | Capacitor - Power                      |
| Header  | 6   | Header total                           |
| 1x03    | 2   | Header, J1 and J2                      |
| 1x06    | 1   | Header, TTL Serial, H1                 |
| 2x03    | 1   | USB1                                   |
| 2x08    | 1   | USB2                                   |
| 1x36    | 1   | Edge connector, H2 (optional)          |
| 1x40    | 1   | Edge connector, H2 (optional)          |
| CH375   | 1   | USB module                             |
| FTDI    | 1   | USB to TTL serial                      |

Note: Three capacitors, C14-C16, are not present in the schematic.

A more complete table, showing component IDs:

| ID                | Part    | Qty | Description                            |
|-------------------|---------|-----|----------------------------------------|
| ----------------- | IC      | 8   | IC        total                        |
| U1                | Z80     | 1   | CPU                                    |
| U2                | 61512   | 1   | RAM                                    |
| U3                | 28C256  | 1   | EEPROM                                 |
| U11               | 16C550  | 1   | UART                                   |
| U8                | 74HC02  | 1   | NOR                                    |
| U5,6              | 74HC32  | 2   | OR                                     |
| U7                | 74HC14  | 1   | NOT                                    |
| ----------------- | R       | 14  | Resistor  total                        |
| R6                | 470R    | 1   | Resistor  - CPU clock                  |
| R1-3, R10, R16    | 1k      | 5   | Resistor  - LED                        |
| R7                | 1k5     | 1   | Resistor  - UART clock                 |
| R4, R8-9, R13-15  | 10k     | 6   | Resistor  - Pull down (3), pull up (3) |
| R5                | 1M      | 1   | Resistor  - CPU clock                  |
| ----------------- | C       | 15  | Capacitor total                        |
| C5,6              | 8 pF    | 2   | Capacitor - CPU Crystal                |
| C18               | 22 pF   | 1   | Capacitor - UART Crytal                |
| C17               | 47 pF   | 1   | Capacitor - UART Crytal                |
| C3-4, C7-13       | 100 nF  | 8   | Capacitor - Decoupling                 |
| C2                | 1 µF    | 1   | Capacitor - Interrupt                  |
| C1                | 10 µF   | 1   | Capacitor - Reset                      |
| C8                | 47 µF   | 1   | Capacitor - Power                      |
| ----------------- | Header  | 6   | Header total                           |
| J1, J2 (P1, P2)   | 1x03    | 2   | Header, J1 and J2                      |
| H1                | 1x06    | 1   | Header, TTL Serial, H1                 |
| J5     (U10)      | 2x03    | 1   | USB1                                   |
| J6     (U10)      | 2x08    | 1   | USB2                                   |
| H2                | 1x36    | 1   | Edge connector, H2 (optional)          |
| H2                | 1x40    | 1   | Edge connector, H2 (optional)          |
| ----------------- | Switch  | 3   | Switch total                           |
| SW1-3             | Switch  | 3   | Push button                            |
| ----------------- | LED     | 5   | LED total                              |
| LED1-5            | LED     | 5   | Power, user, halt, rom, disk           |
| ----------------- | Other   | 2   | Other total                            |
| U10               | CH375   | 1   | USB module                             |
| TTL serial        | FTDI    | 1   | USB to TTL serial                      |



## Additional "homebrew" notes

See [Homebrew](documentation/Homebrew/Homebrew.md) for some rough auxiliary notes about homebrew retro SBC systems.

[Or put on separate repo?]

## TODO

 - Rename XTAL to X1 and X2 instead of Y1 and Y2?
   - X1 and X2 renamed Y1 and Y2, as KiCAD auto named
 - Rename Headers and Jumpers? H1 or J1? P1 or J1?
   - P1 and P2 renamed J1 and J2, as they are jumpers
   - H1 and H2 are actually headers, renamed from KiCAD default of J1 and J2
   - J5 and J6 are not jumpers, but connectors to the CH375S board
 - Add ZIF for EEPROM?
   - It is smaller without ZIF
   - ZIF is ugly?
   - ZIF is unnecessary for an unmodified board, i.e. fixed ROM
   - ZIF is useful for "playing about" – reduces wear, damage, etc..
 - The OR gates in the original schematic look awful and are inconsistent with the NOR gates, which *are* correctly depicted.
 - Modify symbol title 72LS32 -> 74HC32?
 - Are all of the ceramic caps silkscreened as polarised caps? There are only three electrolytic caps (1, 10, and 47 µF)
