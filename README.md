# Z80_Playground
A repo containing info for the Z80 SBC, designed by John Squires

# Z80_Playground

Or [playgroundZ80](https://github.com/greenonline/playgroundZ80)!!!

## Preamble

John Squires, of the now defunct [8bitstack.co.uk](https://8bitstack.co.uk), and the YouTube channel, [John Squires](https://www.youtube.com/@CircuitBreaker256), created a very nifty Z80 SBC, with 32 kB of ROM and 64 kB of RAM, called *Z80 Playground*, that could run CP/M and Tiny BASIC, amongst other things. 

Whilst it is now pretty difficult to find much info out about its design, he did mention that an earlier iteration upon breadboard, was based upon the *Four IC Z80 SBC* – in the videos, he refers to similarity of the breadboard version to the "4 IC Z80" design – which is, most probably, this project, [A 4\$, 4ICs, Z80 homemade computer on breadboard](https://hackaday.io/project/19000-a-4-4ics-z80-homemade-computer-on-breadboard/). 

Unfortunately, around 2022, new videos ceased to be posted, and the whole project seemed to have died. The Wayback Machine shows 8bitstack.co.uk as unresponsive on [8 June 2022](https://web.archive.org/web/20230621025919/http://8bitstack.co.uk/), and the domain was up for sale by [Feb 21 2023](https://web.archive.org/web/20240221232442/https://8bitstack.co.uk/). The last good snapshot was on [April 13 2022](https://web.archive.org/web/20230413220854/https://8bitstack.co.uk/).

This is the best image of the PCB and components that I could find, via [a sold out eBay listing](https://www.cafr.ebay.ca/itm/114754711447) on eBay in Canada, from 2021 – even though the year is not shown in the listing, 2021 is the last year that April 7 fell on a Wednesday (Mercredi):

[![PCB v1.2][1]][1]

There don't appear to be any parts lists, schematics, PCB layouts, Gerber files, etc. – basically, there seems to be little in the way of hardware documentation, apart from the videos. However, there are still Github repos for the software, that are still up, so that is good.

However, using the Wayback machine I managed to get hold of some PDFs of the schematic diagrams for v1.1 and v.1.2, and some additional software, see the section **Wayback data** below. 

While I couldn't find any PDFs of the v1.0 schematic digram, I did manage to get some screenshots of the v1.0 schematic digram, from a video. See the section **Screenshots** below.

In the same video, [Z80 Playground - the Single Board Computer that runs CP/M](https://www.youtube.com/watch?v=CIgxkcXNp1w), at [1:45](https://www.youtube.com/watch?v=CIgxkcXNp1w&t=105), John states that the schematics (for v1.0) were drawn in **EasyEDA** and there is no reason no to assume that the same package was used for the v1.2 schematics.

From the schematic diagrams, using KiCAD 6, I managed to recreate the schematics and the PCB, for v1.2.

I reused, where I could, the Squires '*forward-slash-and-lowercase-camelcase*' type of annotation – even though it feels rather inconsistent and messy/awkward.

The board sold by 8bitstack.co.uk was, I believe, a 4 layer board – in the video, [Z80 Playground - the Single Board Computer that runs CP/M](https://www.youtube.com/watch?v=CIgxkcXNp1w) at [7:46](https://www.youtube.com/watch?v=CIgxkcXNp1w&t=466), John Squires states that he prefers to have a front power plane and a rear ground plane, hence a four plane board. However, I opted to use a simpler two layer board, as the frequencies involved are less than 10 MHz.

In addition to the original Squires version, I also made two other variants: 

 - A (IMHO) better annotated version (`GOL`, AKA `MJ`, variant), using a shorter (more standard) '*uppercase-and-underscore*' form of annotation, and; 
 - A number of versions using the various forms of the [RC2014/RCBus](https://smallcomputercentral.com/rc2014-bus/specification-rc2014-bus/) (`RCBUS`/`RCBUS40`/`RCBUS80`/`RCUS80/40` variants), that should make the board a bit more useful, *if* you so happen to have an RC2014 lying around – see [playgroundZ80](https://github.com/greenonline/playgroundZ80), or the section **RCBUS variants** below.

There is also a version arising from my *initial attempt*, that has two styles of annotation: the Squires 'forward-slash-and-lowercase-camelcase' type and a shorter (more standard) 'uppercase-and-underscore' form of annotation. This is the so-called `dual version` variant. I have retained this as a starting point for other variants, but it should not be used as a complete board design.

I have also had to make some changes relating to how KiCAD works, do the resulting schematics will not match exactly.

I also "tidied up" a few errors, inconsistencies, and omissions.

For the PCB, I had to guess what footprints to use, so they may not match the original PCBs, produced by John Squires, exactly. See the section **Footprints used** below. 

For information about the layout, or the routing of the PCB, refer to the respective **Layout** and **Routing** sections below.

There is a needless **Routing status** section below, that contains a table, of sorts, showing the latest routing results, showing the number of vias used. There may be irregular updates to this table, as and when new improved routing results are achieved for particular boards.

Here is a screenshot of the PCB and 3D view of the RCBUS80 variant:

[![PCB and 3D image][2]][2]

## See also

 - [playgroundZ80](https://github.com/greenonline/playgroundZ80), an RCBUS (RC2014) variant of the Z80 Playground.
 - [Z80 microcomputer on breadboard](https://gr33nonline.wordpress.com/2023/04/29/z80-microcomputer-on-breadboard/)

## Links

### RC2014

 - [RC2014](https://rc2014.co.uk/)
 - [RC2014 bus specification](https://smallcomputercentral.com/rc2014-bus/specification-rc2014-bus/)
 - [lectronz.com](https://lectronz.com/products/search?q=rc2014)

### 8bitstack.co.uk

From the [Wayback Machine for 8bitstack.co.uk](https://web.archive.org/web/20210000000000*/8bitstack.co.uk):

 - [Schematic v1.1 and v1.2](https://web.archive.org/web/20210106120858/http://8bitstack.co.uk/) from 8/1/2021
 - [More links, z80ccp](https://web.archive.org/web/20210508135102/http://8bitstack.co.uk/)
 - [Even more links, sd.com, z80ccp, core_jump, 2048](https://web.archive.org/web/20211020202250/http://8bitstack.co.uk/)
 - There are many *other* snapshots of the site, present on the Wayback Machine, that I have not investigated, due to time constraints. I only checked the earliest three snapshots or so.

### Scribd

Schematics:

 - [v1.1](https://www.scribd.com/document/489322111/Schematic-Z80-playground-v1-1)
 - [v1.2](https://www.scribd.com/document/636188052/Schematic-Z80-playground-v-1-2)
 
### Z80 Playground based projects

 - [A self-contained CP/M computer based on the Z80 Playground](https://kevinboone.me/z80pg.html)
 - [John Squires "Z80 Playground"](https://www.mccrash-racing.co.uk/philg/z80playground/playground.htm)
 - [Building a Z80-MBC3 standalone computer](https://www.digitalplayground.be/?p=6292)
 - [Having fun with CP/M on a Z80 single-board computer.](https://blog.steve.fi/having_fun_with_cp_m_on_a_z80_single_board_computer_)
 - [RC2014 Modular Z80 System](http://blog.tynemouthsoftware.co.uk/2017/07/rc2014-modular-z80-system.html)
   - More of a review, really.

### Manuals

#### German

 - From [Projekte___Z80-Playground](https://erik-bartmann.de/?Projekte___Z80-Playground):
   - [Danke für den Kauf](https://erik-bartmann.de/userfiles/downloads/Z80/Danke%20fuer%20den%20Kauf%20des%20Z80-Playground.pdf), repo copy: [Danke für den Kauf](xtras/manuals/de/Danke%20fuer%20den%20Kauf%20des%20Z80-Playground.pdf) 
   - [Z80-Playground](https://erik-bartmann.de/userfiles/downloads/Z80/Z80Playground.pdf), repo copy: [Z80-Playground](xtras/manuals/de/Z80Playground.pdf)

### Github

 - [gotaproblem/Z80Playground](https://github.com/gotaproblem/Z80Playground)
   - CP/M CBIOS and ROM Monitor plus CP/M tools for the Z80 Playground
 - [skx](https://github.com/skx) - 100+ repos
   - [skx/z80-playground-cpm-fat](https://github.com/skx/z80-playground-cpm-fat) - archived
     - CP/M for the Z80 Playground that runs on the FAT disk format
   - [Turbo Pascal](https://github.com/skx/z80-playground-cpm-fat/blob/main/TURBO.md)
 - [z80playground](https://github.com/z80playground?tab=repositories) - 9 repos
 - [kevinboone](https://github.com/kevinboone/)
   - [kevinboone/KCalc-CPM](https://github.com/kevinboone/KCalc-CPM)
     - A scientific calculator utility for CP/M 2.2 (no, really)
 - [adzierzanowski](https://github.com/adzierzanowski)
   - [adzierzanowski/z80](https://github.com/adzierzanowski/z80)
     - Zilog Z80 (and Intel 8080) assembler/disassembler for everyone and some other tools for my private Z80 stuff


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

### ICS

 - Z80
 - 61512  (64 kB)
 - 16550
 - 28C256 (32 kB)
 - 74HC14
 - 74HC02
 - 74HC32 x 2

### Parts

 - [UM61512AK-15 SRAM - Atari 600XL remake PCB or Mytek 576nuc 1088xel 1088xld](https://www.ebay.co.uk/itm/267668022170), £5.99+£0
 - [50pcs UM61512AK-15 64K X 8 BIT HIGH SPEED CMOS SRAM DIP-32](https://www.ebay.co.uk/itm/395806180798), £52.82 each+£3.12

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
 
### KiCAD 6 quirks

Not really quirks, but changes, or extra tasks, that I found were required, in order to create the schematic in KiCAD 6.

#### 61512 RAM

I had to create a 61512 RAM IC symbol, within KiCAD, as KiCAD 6 does not natively support it, or provide one.

Available on Github: [61512 for KiCAD 6](https://github.com/greenonline/61512_for_KiCAD_6)

#### 74HC32

As a 74HC32 was not present on KiCAD 6, I had to use a 74LS32 instead – same pinout.

### Layout

Please refer to [Z80 Playground v1.2 - layout](documentation/Z80%20Playground%20v1.2%20-%20layout.md).

### Footprints used

See [Z80 Playground v1.2 - footprints](documentation/Z80%20Playground%20v1.2%20-%20footprints.md) for notes on the component footprints used for the Z80 Playground v1.2 layout.

### Routing

Please refer to [Z80 Playground v1.2 - routing](documentation/Z80%20Playground%20v1.2%20-%20routing.md).

### RCBUS variants

 Following the pinouts shown in [Specification, RC2014 Bus](https://smallcomputercentral.com/rc2014-bus/specification-rc2014-bus/), I made four variants of the board, for the RCBUS:

 - RCBUS40 - 01x40 connector, the standard RCBUS
 - RCBUS - 01x40 connector + two partial headers, the "Enhanced RC2014". This is the same as RCBUS80, but with a partial row 2 
 - RCBUS80 - 02x40 connector, the "Extended RCBUS"
 - RCBUS80/40 - 02x40 connector, the standard RCBUS and row 2 is *not connected*. The 02x40 connector is used purely for improved strength of the physical support.

For these RCBUS variants, visit [playgroundZ80](https://github.com/greenonline/playgroundZ80).

### Missing ZIF socket for ROM?

The original circuit from 8bitstack.co.uk featured a 28 pin ZIF socket for the ROM. I have dispensed with this for multiple reasons:

 - Cost
   - As it isn't strictly necessary, it is a bit of a luxury to have.
 - Maybe you don't need it.
   - Maybe you will got one ROM image and stick with it for life. 
 - Easy to add one
   - If a ZIF *is* required then just put one in the socket – maybe stack a few sockets if additional height clearance, from neighbouring ICs (i.e. the UART), or other components, is required on a populated board.

### Four layer board?

#### Cost

Upgrading a printed circuit board (PCB) from 2 layers to 4 layers typically increases the cost by 30% to 80% at low-cost prototype manufacturers, though traditional or local Western fabricators can charge 200% to 300% more. For small prototype runs, the actual price difference is often just a few dollars or pounds.

Low-Cost Prototyping (e.g., JLCPCB, PCBWay): A small batch of 5 basic 2-layer boards might cost around $2 to $5, while 4-layer boards start around $7 to $14 for standard sizes.

See also [Scott's Z80SBC Part-1: 4-layer PCBs with Eagle and JLCPCB](https://www.youtube.com/watch?v=eFmrUgrpOK0&t=302s)

[When should I switch to a 4 layer board?](https://www.reddit.com/r/PrintedCircuitBoard/comments/1gnvgkv/when_should_i_switch_to_a_4_layer_board/). 

While not strictly required for a simple 8 MHz Z80 board, it *has* made routing a lot simpler, halved the number of vias and eased the use of bypass capacitors due to the lack of GND and VCC traces everywhere.

### Routing status

See [Z80 Playground v1.2 - routing status](documentation/Z80%20Playground%20v1.2%20-%20routing%20status.md)

### Parts list

Please refer to [Z80 Playground v1.2 - parts list](documentation/Z80%20Playground%20v1.2%20-%20parts%20list.md).

### Additional "homebrew" notes

See [Homebrew](documentation/Homebrew/Homebrew.md) for some rough auxiliary notes about homebrew retro SBC systems.

[Or put on separate repo?]

### Important note about CH376S module

Address: `0x10` (16) (A4 only), and *every* `0x10` thereafter.

Note: The 2×3 footprint used should be two 1×3 modules with a slight gap between them. From [CH375 USB Storage](https://rc2014.co.uk/modules/ch375-usb-storage/). Also, 

> There are, however, two module variants, both of which look identical at first glance. The most obvious difference is a singe 1×3 header vs two 1×3 headers. The more critical difference though is the 2×8 pinout. The RC2014 module is designed to take the CH375 module with the 8 data lines, D0-D7 on the very outside pins, and the power and control pins on the inside. The variant with a single 1×3 header has the data lines on the inside pins and the power and control pins on the outside. This latter module will not work with this PCB.

Dimensions: 27.5 x 48 mm

02x08 from 02x03: 23.5 mm

Separation of 01x03 from 01x03: ~0.5 mm

Bottom 2 pins of 02x08 in line with two 3 pins of 02x03

02x08 is 4 mm from edge top and bottom, and 2 mm from edge on the right (outside) of board, and 41 (40.5) mm from left outside edge.

02x03 is 10.5 mm from left outside edge, and 30.5 mm from right outside edge, 22 mm from top edge and ~1 mm from bottom edge


### Serial/power module

It is important to select the correct variant of the Z80 Playground board, depending upon which TTL serial board you intent to use.

See [Z80 Playground v1.2 - serial/power module](Z80%20Playground%20v1.2%20-%20serial-power%20module.md)

Baud rate: 6800

v1.1 connections: `DTR TX RX VCC CTS GND` from [Z80 Playground v1.1 is my Single Board Computer for Assembly Language, Basic and CP/M](https://www.youtube.com/watch?v=y9HNbJzdbpE) at [2:13](https://www.youtube.com/watch?v=y9HNbJzdbpE&t=133)

### Types of board

Before we get into the board identifier, it would be worth explaining the boards:

There are two main "families", depending upon the bus used:

 - The Squires bus variant
 - The RCBUS variant

These are subdivided into another two types:

 - The Squires original:
   - The Squires original
   - The MJ/GOL_ variant:
     - Uppercase markings
     - Flat resistors
 - The RCBUS variant:
   - RCBUS40
   - RCBUS80

Each of these four board types all share a very similar layout (component locations may shift slightly between boards), only the bus is the *main* difference.

Then there are <strike>six</strike> seven sub-variants, which offer different options:

   - R/F - **R**everse or **F**ront mounted bus (Alternatively: **R**everse or **F**orward)
   - T/S - Common FTDI **T**TL, or **S**quires' original, serial board orientation
   - 2/4 - **2** or **4** layer board 
   - C/N - **C**TS is exposed, or **N**ot
   - U/P - VCC is jumpered, or not (**U**npluggable/**P**owered)
   - P/N - **P**ositive or **N**egative edge triggered NMI (not RCBUS40)
   - F/S - **F**ixed or **S**witchable RAM (RCBUS40 and RCBUS80 only; The Squires and MJ/GOL boards will not support external memory boards)
    
Note: No front mounted bus boards have been published, due to excessive number of vias arising through routing, so the `R` is effectively redundant, seeing as *all* of the published boards have reverse mounted buses. Thus, the `F` actually *is* redundant.



### Front and rear side annotations

See [Z80 Playground v1.2 - Front and rear side annotations](Z80%20Playground%20v1.2%20-%20Front%20and%20rear%20side%20annotations.md)


### Changing address of UART

Original addressing: `0x08`, repeating every 8!!! A3 goes direct to CS0 on UART, no decoding

TODO: Add ability to modify address?

 - Make address selectable for UART?
   - Maybe both A3 and A5 (or A4) instead of just A3
   - Maybe either A3 or A5 (or A4) instead of just A3
   - Would need additional logic gate or wired-AND
   - Maybe for Pro version

#### Better decoding

Could combine /M1 and /IORQ to /CS2 – using OR and NOR/NOT, as per /CSUSB – freeing CS1 for an address line, but that would change the address, unless an invertor was used.

Better to free /CS2 for A3 and A4, by moving /M1 and /IORQ to CS1 via two NOR gates: 

 - /M1 to NOR/NOT and /IORQ to NOR to CS1 
 
[![UART M1 IORQ][7]][7]

At the minimum decoding A3 and A4 using a NOR and OR:

 - A3 high to (NOR/NOT) and A4 low to OR and to /CS2

[![UART A3 A4][8]][8]

This reduces repeated addresses to 8-15, 40-57, 72-89, 104-121, 136-153, 168-185, 212-229

However, if having to add an IC or two for the NOR and OR, then it would be better to add a dual quad input OR (744072 exists???), or a quad dual input OR (7432) in tree formation. 

TODO: Connect to what and where?

 - Connect to NOT A3 and a NOR (or, if using two OR and a NOR for A4-A7), then A3 and an AND)

#### Best decoding

Use quad input OR for A4-A7 to LOW. 

Note: Dual quad input OR (744072) may not exist, so three gates from a quad dual input OR (7432) in tree formation for active LOW, or two OR ending with a NOR, for active HIGH.

 - Connect to NOT A3 and a NOR (or, if using two OR and a NOR for A4-A7), then A3 and an AND)

[![UART address decode active HIGH][9]][9]

[![UART address decode active LOW][10]][10]


TODO: Schematic Image???

This reduces repeated addresses to 8 - 15

#### Ideal addressing

Have jumpers for 4 address pins (or 4 DIP switches) to select HIGH or LOW for A4-A7 (via switchable NOT)

TODO: Still need to deal with A0-A2...

#### SMB addressing

Use a 74HCT138 3 to 8 line decoder.

### Disabling the UART

 - UART decoding? 
 - Ability to disable?
 - Remove from socket? Not ideal.
 - Maybe for Pro version
 - Fuller addressing should take precedence

### Changing address of CH375

Original addressing: `0x10`, repeating every 16!!! A0 goes direct ot CH375, plus decoding with A4.

 - Make address selectable for CH375?
   - Maybe both A4 and A5 (or A3) instead of just A4
   - Maybe either A4 or A5 (or A3) instead of just A4
   - Would need additional logic gate or wired-AND
   - Maybe for Pro version

Note: Why was U8A (NOR) used as an invertor when there is a spare invertor? Maybe it was due to locally of the NOR as opposed to the NOT gate which is right across the board – same issue as I had with the negative edge NMI.

#### Best decoding

Use quad input OR for A3, A5-A7 to LOW

Note: Dual quad input OR (744072) may not exist, so three gates from a quad dual input OR (7432) in tree formation for active LOW, or two OR ending with a NOR, for active HIGH.

 - Connect to NOT A4 and a NOR (or, if using two OR and a NOR for A4-A7), then A4 and an AND)

TODO: Schematic Image???

This reduces repeated addresses to 16 - 23. Although due to A0, then the four repeated base addresses would be:

 - 16
 - 18
 - 20
 - 22

#### Ideal addressing

Have jumpers for 4 address pins (or 4 DIP switches) to select HIGH or LOW for A3, A5-A7 (via switchable NOT)

TODO: Still need to deal with A1 and A2...

#### SMB addressing

Use a 74HCT138 3 to 8 line decoder.


### Disabling the USB CH375

Although easy to implement, it is not *really* required as the daughter board can just be removed - Fuller addressing should take precedence


 - Make CH375 disabled
   - You can just unplug it!
   - In case of conflicts with other boards on bus, or other storage board is used.
   - USB is disabled: If input to U6B is held high, so both inputs to U8D is held LOW
     - Jumper to GND or A4: *both* U8D inputs 
       - Another variant: U/N (USB/Not)
       - This is pretty essential for compatibility for RCBUS
     - Note: Can not use /M1 and U8A in the same manner as A4, because M1 flips, and would need to stay 
   - Jumper to connect to U6B output or to pull high
   - Maybe for Pro version

[![Disable USB][6]][6]

### Disabling the RAM

See [Z80 Playground v1.2 - Disabling RAM](Z80%20Playground%20v1.2%20-%20Disabling%20RAM.md)


### `externalNMI` (`EXT_NMI`) not used

Very late in the design process, I realised that I had connected the incorrect NMI signal (`NMI`) to the bus, instead of the "external" NMI line (`EXT_NMI`/`externalNMI`). This had to be rectified.

Despite being an *inconvenience*, it did help in cleaning up some previously unspotted issues, as well as reducing the number of vias in some boards, although increasing them in others.

See [Z80 Playground v1.2 - Fixing the externalNMI debacle](Z80%20Playground%20v1.2%20-%20Fixing%20the%20externalNMI%20debacle.md) for details.

### Have two varieties of NMI triggering for RCBUS

 - Positive edge
   - required routing correction fix
 - Negative edge
   - required two diodes and a pull-up, or a mix of positive and negative logic involving the NOR gate, and an aditional NOT gate.

### Inverting the NMI (for RCBUS) - negative edge trigger

See [Z80 Playground v1.2 - Providing a negative edge triggered NMI](documentation/Z80%20Playground%20v1.2%20-%20Providing%20a%20negative%20edge%20triggered%20NMI.md) for the board implmentations.

See [Z80 Playground v1.2 - Inverting the NMI (for RCBUS) - negative edge trigger](documentation/Z80%20Playground%20v1.2%20-%20Inverting%20the%20NMI%20(for%20RCBUS)%20-%20negative%20edge%20trigger.md) for the design.

## TODO

(Most of these have actually been done, just not marked as such)

 - Rename XTAL to X1 and X2 instead of Y1 and Y2? **DONE!**
   - X1 and X2 renamed Y1 and Y2, as KiCAD auto named
 - Rename Headers and Jumpers? H1 or J1? P1 or J1? **DONE!**
   - P1 and P2 renamed J1 and J2, as they are jumpers
   - H1 and H2 are actually headers, renamed from KiCAD default of J1 and J2
   - J5 and J6 are not jumpers, but connectors to the CH376S board
 - Add ZIF for EEPROM? **DONE!**
   - It is smaller without ZIF
   - ZIF is ugly?
   - ZIF is unnecessary for an unmodified board, i.e. fixed ROM
   - ZIF is useful for "playing about" – reduces wear, damage, etc..
 - The OR gates in the original schematic look awful and are inconsistent with the NOR gates, which *are* correctly depicted.
 - Modify symbol title 72LS32 -> 74HC32?
 - Why is C1 10µF but C2 is 1µF?
 - Change J5 from `Conn_02x03_Odd_Even`
 - Change J6 from `Conn_02x08_Odd_Even`
 - Change J5 and J6 to H5 and H6? As they are headers?
 - RCBUS should use/provide the extended 80 pin variant.
 - Should version number not be 1.2, confusing? Maybe 1.2.0.1, 1.2.0.2, 1.2.0.3, 1.2.0.4, or  1.2.0.1s, 1.2.0.1g, 1.2.0.1r,  or  1.2.0.1squires, 1.2.0.1gol, 1.2.0.1rcbus. etc.
 - Should I try to manually trace the Squires PCB tracks? 
 - The decoupling capacitors are not autorouted to their ICs correctly – might need to manually do that first!
 - Flip RC2014 bus
 - Align CH376S connector
 - Check all overlaps
 - Flip lower left two capacitors on Squires - DONE
 - Orientation of H6 and H5? VCC should be lower left.
 - Top row of 02x03 level with bottom row of 02x08
 - Create a Squires to RC2014 adapter?
 - Check if some RCBUS connectors are reversed
 - Swap J7 and J8, check all boards..!!! 
   - GOLr is bad. - DONE! aligned2
   - Squiresr is bad - DONE! aligned2
 - GOL: C8 upside down? Shouldn't all electrolytic capacitors face the same way? - DONE! aligned2
 - Move J1 and J2 together? - No, not in original design, so leave it
 - Bypass caps - bodge wires?
 - Moving switches higher (like GOL) gives more room for RAM traces?
 - Move R8C1C2R15 closer together?
 - Drill 4 holes - DONE!
   - The holes should really be in the same place on all boards, to provide consistent mounting points
   - Use a "group" and copy between boards for consistency
 - Outline of PCB - DONE?
 - Add a note about forward and reversed bus connectors
 - RCBUS only has 39 pin connector!!! Doesn't matter though as the schematic and PCB layout is only "for show" – use the RCBUS80 board just partial pins instead.
 - Must change/increment version number from v1.2
 - Should there be notes on the RCBUS routing, in the standard Z80 Playground repo? Belongs to the playgroundZ80 repo. Have two separate or lump all together? Better to have separate, else too busy and confusing – too many board variants!
 - Squiresr: C8 is too close to U11: Move right
 - Squiresr: Align J1 and J2 - DONE! aligned2
 - Fill VCC and GND planes on front and rear respectively? Is that a good idea? Are you creating a capacitor out of the PCB? Shouldn't all areas by GND? Did he use a four-layer board?
   - [Can you have a ground plane and a VCC plane right next to each other when designing a PCB?](https://electronics.stackexchange.com/questions/715575/can-you-have-a-ground-plane-and-a-vcc-plane-right-next-to-each-other-when-design)
   - [What are the drawbacks to a Vcc (positive voltage) plane](https://electronics.stackexchange.com/questions/13493/what-are-the-drawbacks-to-a-vcc-positive-voltage-plane)
   -  [Best Practices for Implementing Power and Ground Planes in PCB Design](https://www.allpcb.com/allelectrohub/best-practices-for-implementing-power-and-ground-planes-in-pcb-design)
 - Should the VCC and GND planes be internal?
 - Rename forward to front, and reverse to rear?
 - Move serial port down? Dimensions of serial board? 35-38 mm
 - Fix all silk screen markings - DONE
 - Round off board corners?
 - Change REF to HL for holes.
 - Major worries:
   - Hole 1 need to be below the CH376S module!
     - Add HL5, there should be space. Shift C11 down if need be
   - Crystal should be next to UART really, even though not in original.
   - Crystal should be next to Z80 really, even though not in original.
     - However, the Crystal feeds U7, close by so it is probably ok.
   - Crystal should not be by edge of board, even though it is in original.
   - Bypass caps to both GND and VCC
 - C9 incorrect orientation!!! Check others
   - No it isn't, it is perfect, as Z80 has VCC on the left.
 - Properly renumber components
   - For PRO version only?
 - Add marker for CH376S on front of board
 - Hide the connector's silkscreen - DONE!
 - Make OMRON button variant.
 - Check HL5 on all PCBs with holes.
   - The original placement was ok, no need to move halfway down
   - Move all halfway down hole PCBs in a separate directory, as they are redundant and confusing, and cluttering.
 - Need a better naming convention, it is currently all over the place
 - Add TTL Serial silkscreen (original has this)
 - TTL Serial connector is the wrong way around on Squires, and probably all.
   - My orientation might actually be better:
     - The orientation of the serial board is matching the orientation of the mother board as the bottom is also facing the bottom, rather than having bare electronics facing down, as in the Squires original.
     - Easier to route, to boot! One less via!
     - Although, it would obscure any "blinken LEDs" on the top side of the serial board
 - The DTR from the serial board is not routed. Is that a problem? In the video [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them
](https://www.youtube.com/watch?v=MaolTlk7XKM) at [1:10](https://www.youtube.com/watch?v=MaolTlk7XKM&t=70), it can be seen that there is a DTR pin on the serial board, and that there "might" be a trace coming from the connector for that pin, although it is unclear whether it is an joining track. Although DTR is not marked on the front silkscreen for the pins, nor is it in the schematic. TODO: Where on the UART would it go? Which pin? Pin 33, and it goes to the "user" LED.
 - Add pins silkscreen for CPU (original has this) - DONE!
 - Add pins silkscreen for bus (original has this) - DONE!
 - Add silkscreen version
 - Add silkscreen variant
   - Variant code: 
     - R/F - reverse or front mounted bus
     - T/S - Common FTDI, or Squires' original, TTL orientation
     - 2/4 - 2 or 4 layer board 
 - Add silkscreen date
 - Silkscreen TTL serial pins (forward)  - DONE!
 - Silkscreen TTL serial pins (and reversed)  - DONE!
 - Silkscreen J1 and J2  - DONE!
 - The J1 and J2 are wrong - GND needs to be in the middle (pin 2), not on pin 3 as per schematic v1.0. Also, check which pins are top (pin 1) and bottom (pin 3). Presumably j goes on the bottom? So swap pins 2 and 3?
   - Isn't ROMon left floating, if /romonj is selected?
     - No. ROMon is an output
 - Silkscreen U10 & outline of CH376S card - DONE!
   - GOL has differing placement from Squires, and RCBUS40 and RCBUS80 board.
 - Silkscreen RCBUS, at least pins 1 and 40 - DONE!
 - Put reverse bus labels on underside - DONE!
   - [Flip words](https://phrasefix.com/tools/flip-words/) 
 - Put two rows of reverse bus labels on underside of RCBUS80, correctly placed
 - Put reverse CPU labels on underside - DONE!
 - Have variant added in box on underside (as well as the front)
 - Have variant explanation in box on underside
 - Have variant added in each board's README
 - Have variant explanation in each board's README
 - Have variant added in each board's PCB sheet in KiCAD, but not the schematic (which should be 1.2.1)
 - Have 1.2.1 put in every schematic diagram
 - Ensure bypass caps on all 4 layer boards, and as best possible on 2 layer (list the bad boards that will need external cap added)
 - Put Unofficial Backplane-80 Pin-outs, from [RC2014](https://smallcomputercentral.com/rc2014-bus/specification-rc2014-bus/) on RCBUS80 silkscreen? 
   - No need, extended BP80 pins not wired up.
 - Document the strings used (including spaces) for the pins' labels.
 - Should 8bitstack.co.uk silkscreen be applied?
   - No, as the website is dead
   - Yes, as it maintains authentic feel
   - No, as not having it makes for an easy differentiation that this is a reverse engineered job.
 - RCBUS variants could route DTR? **DONE!** -> Not doing!
   - RCBUS80r5cp2fixed4z can, with jumper
   - RCBUS80r5cp2fixed3z can, with jumper
   - RCBUS80r5gz can, with jumper
   - RCBUS80r5fz can, with some rerouting of VCC, with jumper
   - RCBUS40r3jz can not, not without a via, maybe with jumper
   - RCBUS40r3iz can not, not without a via, maybe with jumper
   - RCBUS40r3ipz can, with jumper
   - RCBUS40r3ip2z can, with jumper
   - SQUIRES aligned4b6z could with rerouting of blue line, maybe not jumper
   - SQUIRES aligned4b4z could with rerouting of blue line, maybe not jumper
   - No, as DTR has been repurposed for reseting Arduinos.
     - Extracting CTS would be much more useful for the host to slow down the Z80 playground, should the host be a slower machine, i.e. another slower CP/M machine
       - Yes! This! ^^^^^^^^
       - The SmallComputers RC2014 serial boards come with a TTL serial board that has both RTS *and* CTS, not RTS and DTR
         - RTS RX TX 5V CTS GND (component side up, from left)
         - TODO: compare with usual FDTI TODO Check this:
           - GND RTS VCC RX TX!!! (This might be correct, but reversed for both CTS/RTS n TX/RX, if RTS is CTS <- TODO: Check this!)
           - TX RX VCC RTS GND (component side up, from left)
         - TODO: compare with Squires FDTI TODO Check this:
         - If different, then it should really use the correct serial board, instead of the Arduino RESET_DTR/upload board (i.e. the red FTDI should not be used, or have connectors provided for).
           - Do this in a PRO version of the board, or playground Z80
             - Should retain original Z80Playground replica status as someone may need, or depend upon, the original style TTL boards, as originally intended by Squires
               - but could just re-route and add another sub variant, as was done for T/S sub variant, so C/T/S, with C being the new CTS/RTS board
                 - but which way up and down of the CTS board is also important, as it was for T/S, so not C/T/S but rather T/S, as before, and C/R for CTS  (component side up) and reversed (component side down)?
 - Do bypass capacitor check and make a table/document <--- This!!! **DONE!**
   - Add to candidate table
   - RCBUS40r3ip2z needs a via to add GND to UART
   - If vias are needed then so be it, especially on the lower via count boards, numbering in the 20s.
 - Distance of TTL serial? Check and make table
 - Move up the edge bus on bus80, and gol? Reduce warnings to zero?
 - Remove the needless 61512 files from every board: `Memory_RAM_PC61512.kicad_sym` and `Memory_RAM_UM61512.kicad_sym` and `Memory_RAM_61512.bak` and `Memory_RAM_PC61512.bak`
   - Maybe not, as the symbol editor complains
 - Bring out CTS for RCBUS80
   - Maybe other variants later
 - RCBUS variants could route CTS? - **DONE!**
   - RCBUS80r5cp2fixed4z
   - RCBUS80r5cp2fixed3z
   - RCBUS80r5gz
   - RCBUS80r5fz
   - RCBUS40r3jz
   - RCBUS40r3iz
   - RCBUS40r3ipz
   - RCBUS40r3ip2z
   - SQUIRES aligned4b6z 
   - SQUIRES aligned4b4z 
     - but could just re-route and add another sub variant, as was done for T/S sub variant, so C/R, with C being the new CTS/RTS board (component side up), and R the reversed (component side down)
 - Add black and white PDF, PNG for the two PCB sides of 2-layer
 - Need a checklist f things to check
   - But it is everything! Check everything!
 - Need to have silkscreen and component markings "template to group and paste on each type of board (for 2- and 4 layer, the T/S should have the same markings, apart from the serial port markings, obviously)
   - Get screenshots of the T, and make the S the same (apart from the serial port markings, obviously)
 - Silkscreen: Put board type/version on bottom right of board 
 - Silkscreen: Put URL on board
 - Reduce number of variants? :
   - If TTL board was mounted vertically then less of an issue
     - But which side, or leave it to user?
   - Specify only works with Cousins' TTL board?
     - No, as original board used wierdo and must be compatible
       - Best option is the current one, support all TTL boards
 - Quote: "Harder to reverse-engineer someone else's work than to start afresh and create a new PCB layout."
 - Featured at top of Github page: RCBUS40/80 support CTS
 - Can't put URL on front bottom, no room due to bus
 - U10 differs in size, Make consistent
 - Group silkscreen elements into a template that can be pasted between boards
 - Take screenshot of one silkscreen and make the others the same, manually
 - Personally, physically create only 4-layer Squires RS4 (as original was also 4-layer), and 2-layer RCBUS80 RT2 (for it's simplicity and reduced cost).
 - Do a RCBUS80 with the bus shifted up one; and two and HL3 and HL4 shift up one., as a test  - **DONE!** pGd01 (bus+1 only), pGd02 (bus+2 and holes+1), pGd10 (holes+2) - meh...
 - I should route an RCBUS80 RT2 manually, to see if I can do better than the autorouter..!
 - Should VCC on the TTL connector be jumpered, in case board is attached to a bus? Conflict with computer power supply?
 - 1MOhm res parallel with UART XTAL, according to [16550 datasheet](https://www.ti.com/lit/ds/symlink/tl16c550c.pdf) 
 - Manually route Pro
 - Manually add a CTS line to an RCBUS80 RT2 clone, to see if via is any less: RCBUS80r5fz9 -> RCBUS80r5fz9a - **DONE!**
 - PCB Candidate table, not list
 - Jumper the VCC pin to the serial TTL board? As per the Z180 CPU board, [Z80 Retrocomputing 18 – Z180 CPU Board for RC2014](https://www.smbaker.com/z80-retrocomputing-18-z180-cpu-board-for-rc2014) - **DONE!**
   - This is kind of essential, isn't it? To avoid power conflicts, if plugging in to a (*powered*) backplane
   - Is there room?
   - All variants except Squires?
     - Only RCBUS variants, as MJGOL_ and Squires have no bus
     - DONE! On *all* variant and boards, with CTS
     - DONE! Should do for non-CTS, as well?
   - Add a new sub-variant (which will be the default) `U/P` - Unpowered/Powered.
 - Drop in resistors for the serial TTL board? As per the Z180 CPU board, [Z80 Retrocomputing 18 – Z180 CPU Board for RC2014](https://www.smbaker.com/z80-retrocomputing-18-z180-cpu-board-for-rc2014)
   - Unlikely that there is room
   - With a jumper? Or solder spots?
   - Connected to what?
   - What are they for?
     - For protection?
       - [Why use a series resistor between Arduino RX and ESP8266 TX?](https://electronics.stackexchange.com/questions/431868/why-use-a-series-resistor-between-arduino-rx-and-esp8266-tx)
       - [Properties of Pins Configured as OUTPUT](https://docs.arduino.cc/learn/microcontrollers/digital-pins/)
     - For ringing?
 - Pull-up resistors for NMI, INT, BUSRQ, WAIT, DMA? As per the Z180 CPU board, [Z80 Retrocomputing 18 – Z180 CPU Board for RC2014](https://www.smbaker.com/z80-retrocomputing-18-z180-cpu-board-for-rc2014) **DONE!** see **Pull-ups** below.
   - Unlikely that there is room
   - Why?
   - Are the necessary?
   - Should they be on the backplane instead of per board?
   - TODO: Check [RCBUS specification](https://smallcomputercentral.com/rcbus/)
     - `/INT` should have a pull-up resistor - do for RCBUS variants
   - Already pulled up! INT, BUSRQ and WAIT
   - [Z80 RC2014 schematic](https://8b8bf43264c2f150841a.b-cdn.net/wp-content/uploads/2017/04/Z80-CPU-Rev-1_3.pdf) shows: INT, NMI, BUSRQ and WAIT pulled up
   - Just need to add NMI
   - [Question about pull-up resistors for the INT, NMI, BUSRQ, and WAIT pins.](https://www.reddit.com/r/Z80/comments/175h7yn/question_about_pullup_resistors_for_the_int_nmi/)
 - Jumpers for BUS pins: BUSRQ, BUSACK, HALT, WAIT, Rx, Tx (or additional address lines)? As per the Z180 CPU board, [Z80 Retrocomputing 18 – Z180 CPU Board for RC2014](https://www.smbaker.com/z80-retrocomputing-18-z180-cpu-board-for-rc2014)
   - Unlikely that there is room
   - Are they necessary?
 - `PAGE` pin on RCBUS 80 or 64, see [RCBUS specification](https://smallcomputercentral.com/rcbus/)
 - Does the positive edge triggered /externalNMI need to be changed for RCBUS? 
   - Yes, of course! See section **Inverting the NMI (for RCBUS) - negative edge trigger**
 - No debounce on NMI switch
 - Make a table of variants and which are available (previously all were available, but now not RCBUS for positive edge triggered, as totally incompatible with RCBUS!)
 - The CPU pin labels would be much better if individually placed  vertically – either away from or, if space, toward the centre of the Z80 – and grouped
 - The bus pins would be much better if individually placed
   - Squires
   - MJ/GOL_
   - RCBUS40
   - RCBUS80 
 - Change all data and address lines to lower case on Squires only
 - Ensure all data and address lines to upper case on non-Squires board - **DONE!**
 - Open source hardware silkscreen logo [13:05](https://www.youtube.com/watch?v=AQTJlVj3B8E)
 - Why are TX, Rx, IEI and IEO not connected on the bus of RCBUS40? 
   - Have jumpers to connect to bus?
 - TODO: Update vias in PCB candidate via/err/warn table since the NMI issue
 - Add "EXT_NMI not used on RCBUS40 bus" note on schematics of RCBUS40 - **DONE!**
 - Placement of the jumper to serial power is inconsistent
 - Remove `aligned` and `fixed` from the variant names, as they probably mean the same thing, and it is ancient history. SO long as a note is made of the name change then the chain of history is preserved. replace with `a` or `f`, just to retain a marker of the past?
 - What TTL family? It *should* be HCT, I believe.
   - Use LS symbols and rename HCT?
 - Add ability to disable ROM and RAM on board, so that an external 512K can be used. **BONE!**
   - Yet another variant: S/F (**S**witched, **F**ixed)
     - Add jumper to disable RAM, to VCC on CE
     - ROM is already jumpered, up with the two three pin jumpers. add a new jumper.
   - Only for RCBUS80 and RCBUS40, as Squires Bus has no boards.
   - Make Pro version have 512K ROM and RAM
 - Add Squires schematic to this readme
 - Make address selectable for CH375?
   - Maybe both A4 and A5 (or A3) instead of just A4
   - Maybe either A4 or A5 (or A3) instead of just A4
   - Would need additional logic gate or wired-AND
   - Maybe for Pro version
 - Add ability to disable CH375 **DONE!**
   - You can just unplug it!
   - In case of conflicts with other boards on bus, or other storage board is used.
   - USB is disabled: If input to U6B is held high, so both inputs to U8D is held LOW
     - Jumper to GND or A4: *both* U8D inputs 
       - Another variant: U/N (USB/Not)
       - This is pretty essential for compatability for RCBUS
     - Note: Can not use /M1 and U8A in the same manner as A4, because M1 flips, and would need to stay 
   - Jumper to connect to U6B output or to pull high
   - Maybe for Pro version
 - Disabling the RAM could be done similarly by jumpering both inputs to U8C to /WANTROM or GND, thereby saving on the additional OR gate (U6C?)
 - On Easy Z80, but missing on ZPG:
   - Power jack? Ironically, Z80 Playground v1.1 did have a 5 V DC power jack
     - Not needed, extra bulk, power from USB or BUS
   - RESET MAX693
   - PAGE_EN?
 - Make USB IO address configurable, in order to avoid any potential conflicts? What is the USB IO address? `0x10`, only using A4
 - Check serial (FTDI, squires, SCS) boards connection pin order again
 - Group silkscreen for copy and paste - some adjustments will be required probably, on a per board basis
 - Put the Github URL, vertically orientated, along the side of the PCB to avoid the bus **DONE!**
 - Make feature table **DONE!**
   - It may seem obvious, from the variant code, but just make it explicit.
 - Tidy schematic sheets main page:
   - Make equi-sized rectangles
   - Add big labels?
 - UART decoding? Address: `0x08`, repeating every 8!!! Ability to disable?
 - Check all footprints for size.


## Todo: Final checks

 - Footprints
 - Schematic equality
 - Go through the TODO list!

## To do: Things to check on all boards

Ensure:

 - ROM to the left
 - RAM not totally to the right
 - Crystals are shifted left (not down) and close to caps
 - U5 is on the right edge
 - HL 5 is correct and not overlapping.
 - Silkscreen vertical connectors
 - C7 is close to U7
 - Silkscreen TTL serial pins (forward) 
 - Silkscreen TTL serial pins (and reversed) 

Put:

 - Title on PCB sheet of nearly complete layouts: 
   - `Z80 Playground v1.2 (Squires RT2 - aligned4b4z6 - reversed connector, std. TTL, 2-layer)`
   - `Z80 Playground v1.2 (MJ/GOL RT2 - alignedcz - reversed connector, std. TTL, 2-layer)`
   - `Z80 Playground v1.2 (MJ/GOL RT4 - aligned2pc2z - reversed connector, std. TTL, 4-layer)`
   - `Z80 Playground v1.2 (MJ/GOL RS4 - aligned2pc3z - reversed connector, Squires TTL, 4-layer`
   - `Z80 Playground v1.2 (MJ/GOL RS2 - alignedez2 - reversed connector, Squires TTL, 2-layer`
 - Silkscreen info box for underside

## Running RomWBW

Would Z80 Playground support RomWBW, or rather, does RomWBW support the Z80 Playground and the USB reader?

See [Z80 Playground v1.2 - Running RomWBW](documentation/Z80%20Playground%20v1.2%20-%20Running%20RomWBW)

## Best board designs

See [PCB Candidates](documentation/Z80%20Playground%20v1.2%20-%20PCB%20candidates.md)  

## Main board variants
 
  - Z80 Playground
    - a replica
  - playgroundZ80
    - a PRO version with improvements, see **Pro board feature**.
  - Z80 PlaygroundRC
    - a replica but with RCBUS40/80
  
# A new start... a new hope

## Pro board features

A PRO version with the improvements:

 - bypass capacitor placement (next to GND)
 - SMD pre-mounted bypass 1 µF capacitors
 - bypass capacitor's IDs match their IC's ID (i.e. C5 -> U5)   
 - TTL pin order
 - CTS? <---- THIS!!!
 - Closer XTAL to UART
 - CPU XTAL not on edge of board
 - Also re-annotates components 
 - Make a proto PRO version for fun: Crystal close to UART, etc.
   - RCBUSPro only supports cousins CTS TTL board, underside, which orientation?
   - DONE, and failed to route..!
 - Bigger ROM?
 - Paged RAM?
 - BP80 only
 - bypass capacitors next to ground pin, not VCC
 - 1 M&Omega; res parallel with UART XTAL
 - what else?
   - Banking
   - Can disable RAM and ROM, if not 512kB and need external board
     - Add jumper to disable RAM, to VCC on CE
     - ROM is already jumpered, up with the two three pin jumpers. add a new jumper.
   - 7408 AND for NMI?
   - 512 kB RAM
   - 512 kB FLASH
   - RomWBW compatibility
 - Make address selectable for CH375?
 - On Easy Z80 but missing on ZPG
   - Power jack?
   - RESET MAX693
   - PAGE_EN?
 - Better (i.e. full) address decoding of IO: 
   - Currently repeating at `0x10` intervals
   - USB, add 8 input NAND, or two 4 input NAND (7420) to replace `U8d`, to map USB to `0xF0` instead of `0x10`. Or use a dual 4 input NOR (7425) and an invertor on A4 to map `0x10` properly
     - Code written for this board would still work on original board, but it would break all original code, which would need tweaking the BDOS.
 - Better (i.e. full) address decoding of UART
   - Currently repeating at `0x08` intervals
 - Redo decoding using NAND (only?)

Also, features added to the basics:

 - CTS
 - Power jumper on TTL
 - Negative edge NMI
 - disable RAM
 - disable USB
 - disable UART?

Note: HL3 and HL4 have been shifted up one notch (or more), from the Z80 Playground boards holes layout. Should shift one more to give space for bus silk screen, but would need to shift U6 and U8 again!

<!-- Images -->

  [1]: xtras/hardware/screenshots/v1.2/ebay/Z80%20Playground%20v1.2%20PCB%20and%20components.jpeg "PCB v1.2"
  [2]: xtras/hardware/screenshots/v1.2.1/PCB_and_3DView_RCBUS80r5cp2.png "PCB and 3D image"

  [3]: xtras/hardware/screenshots/TTL_serial_board/Z80PG_TTL_board.png "Z80 Playground TTL serial board"
  [4]: xtras/hardware/screenshots/TTL_serial_board/Red_FTDI_board.png "Red FTDI TTL serial board"
  [5]: xtras/hardware/screenshots/TTL_serial_board/SCD_TTL_board_hi.jpg "TTL serial board as used by Small Computers Direct"
  [6]: xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20USB%20Disable.png "Disabling USB logic"
  [7]: xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20UART_IORQ_M1.png "UART IORQ M1"
  [8]: xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20UART_A3_A4.png "UART A3 A4"
  [9]: xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20UART_Address_decode_active_HIGH.png "UART address decode active HIGH"
  [10]: xtras/hardware/screenshots/RomWBW_compatibility/Z80%20Playground%20-%20UART_Address_decode_active_LOW.png "UART address decode active LOW"

