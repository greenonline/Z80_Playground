# Z80_Playground
A repo containing info for the Z80 SBC, designed by John Squires

# Z80_Playground

Or [playgroundZ80](https://github.com/greenonline/playgroundZ80)!!!

## Preamble

John Squires, of the now defunct [8bitstack.co.uk](https://8bitstack.co.uk), and the YouTube channel, [John Squires](https://www.youtube.com/@CircuitBreaker256), created a very nifty Z80 SBC, called *Z80 Playground*, that could run CP/M and Tiny BASIC, amongst other things. 

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
 - 61512
 - 16550
 - 28C256
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
 
### Footprints used

See [Z80 Playground v1.2 - footprints](documentation/Z80%20Playground%20v1.2%20-%20footprints.md) for notes on the component footprints used for the Z80 Playground v1.2 layout.

### KiCAD 6 quirks

Not really quirks, but changes, or extra tasks, that I found were required, in order to create the schematic in KiCAD 6.

#### 61512 RAM

I had to create a 61512 RAM IC symbol, within KiCAD, as KiCAD 6 does not natively support it, or provide one.

Available on Github: [61512 for KiCAD 6](https://github.com/greenonline/61512_for_KiCAD_6)

#### 74HC32

As a 74HC32 was not present on KiCAD 6, I had to use a 74LS32 instead – same pinout.

### Layout

Please refer to [Z80 Playground v1.2 - layout](documentation/Z80%20Playground%20v1.2%20-%20layout.md).

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

## Routing status

See [Z80 Playground v1.2 - routing status](documentation/Z80%20Playground%20v1.2%20-%20routing%20status.md)

## Parts list

Please refer to [Z80 Playground v1.2 - parts list](documentation/Z80%20Playground%20v1.2%20-%20parts%20list.md).

## Additional "homebrew" notes

See [Homebrew](documentation/Homebrew/Homebrew.md) for some rough auxiliary notes about homebrew retro SBC systems.

[Or put on separate repo?]

## Important note about CH376S module

Note: The 2×3 footprint used should be two 1×3 modules with a slight gap between them. From [CH375 USB Storage](https://rc2014.co.uk/modules/ch375-usb-storage/). Also, 

> There are, however, two module variants, both of which look identical at first glance. The most obvious difference is a singe 1×3 header vs two 1×3 headers. The more critical difference though is the 2×8 pinout. The RC2014 module is designed to take the CH375 module with the 8 data lines, D0-D7 on the very outside pins, and the power and control pins on the inside. The variant with a single 1×3 header has the data lines on the inside pins and the power and control pins on the outside. This latter module will not work with this PCB.

## Serial/power module

Dimensions (red FTDI): 18 x 36 mm

Not sure that I like the idea of possible shorts – Use captan tape for protection and sticky foam pad for spacing


Silkscreen on the front

```none 
 TX
 RX
 VCC
 RTS
 GND
 
 TTL Serial
```

It should be noted that this pin order is for the strange serial module, with the board component side up, as shown in [Flow Control for UART Serial communication between Z80 Playground and a PC](https://www.youtube.com/watch?v=RFxSKGnuisE) at [8:56](https://www.youtube.com/watch?v=RFxSKGnuisE&t=536):

[![Z80 Playground TTL serial board][3]][3]

```none
DTR RX TX VCC R/C GND (component side up, from left)
```

However, for the more usual cloned FTDI module, with the board component side up, the connnections are in the reverse order..!

[![Red FTDI TTL serial board][4]][4]

```none
 GND  RTS  VCC   RX   TX
```

Of course, one could flip the TTL serial board over in order to realign the pins in the correct order, but then the blinken lights would be obscurred, as they would be facing the undersie of the motherboard. It all depends upon whether you believe that the correct orientation for a *daughter board, mounted beneath the motherboard*<sup>*</sup>, should have its components facing down, or up. In other words, should the underside of the completed unit show only PCB undersides, or, more inconsistantly, the motherboard underside and the TTL serial board's front side? In my mind, the latter is not dissimilar to serving a quiche upside down on a plate.


The TTL serial board used by Small Commputers Central is

[![TTL serial board as used by Small Computers Direct][5]][5]

```none
RTS RX TX 5V CTS GND (component side up, from left)
```

Compare this to a red FTDI board: `GND RTS VCC RX TX`!!! (This might be correct, but reversed for both CTS/RTS n TX/RX, if RTS is CTS <- TODO: Check this!)





 - If different, then it should really use the correct serial board, instead of the Arduino RESET_DTR/upload board (i.e. the red FTDI should not be used, or have connectors provided for).
   - Do this in a PRO version of the board, or playground Z80
     - Should retain original Z80Playground replica status as someone may need, or depend upon, the original style TTL boards, as originally intended by Squires
       - but could just re-route and add another sub variant, as was done for T/S sub variant, so C/T/S, with C being the new CTS/RTS board
         - but which way up and down of the CTS board is also important, as it was for T/S, so not C/T/S but rather T/S, as before, and C/R for CTS  (component side up) and reversed (component side down)?



#### Footnote

<sup>*</sup> IMHO, this is the worst possible orientation for a daughter board. Daughter boards should really mount to the front of a board. However, in this limited-real-estate case, it is understandable why it was done in this manner. The motherboard's own LEDs would be covered by a front mounting daughter board, if the TTL connector were to remain in the same location.

### Front side annotations

The board's identifier consists of two parts:

 - Project version
 - Board variant code

The version number pertains more to the schematic, and the board variant code pertains more to the PCB layout.

The version number of 1.2.1 was chosen to reflect the fact that while the schematic diagram is *essentially the same as the Squires version 1.2*, there may be differences in the schematic that I am unaware of. 

This is because the files pertaining to that design no longer exist,and so this is, unavoidably so, a different version as it has been recreated as best possible, given the limited documentation (as well as the obvious routing differences on the PCB). However, the routing differences, of the subsequent board variantions, are not reflected in the version number, but instead by a six letter description of the base PCB layout followed by a three letter code for the three minor variations of that layout.

All base PCB layout variant codes are the same length (6 characters):

```none
SQUIRES
MJ_GOL_
RCBUS40
RCBUS80
```

Board variant code: 

   - SQUIRES/MJ_GOL_/RCBUS40/RCBUS80 - Base PCB layout variation and bus
   - R/F - reverse or front mounted bus
   - T/S - Common FTDI, or Squires' original, TTL orientation
   - 2/4 - 2 or 4 layer board 
    
Note: No front mounted bus boards have been published, due to excessive number of vias arising through routing, so the `R` is effectively redundant.

Date, Project, version, board variant code:

```none
Aug 2026, Z80 Playground v1.2.1 ([SQUIRES|MJ_GOL_|RCBUS40|RCBUS80][R|F][T|S][2|4])
```

So, for example, for Squires board, with reversed bus, TTL orientation, 4 layer:

```none
Aug 2026, Z80 Playground v1.2.1 (SQUIRESRT4)
```


#### Squires/GOL bus pins

```none
VCC 0v /re /wa /bk /bq /1 nm /rd /wr /mr /io a15 a14 a13 a12 a11 a10 a9 a8 a7 a6 a5 a4 a3 a2 a1 a0 d7 d6 d5 d4 d3 d2 d1 d0
```

Text Height/Width: 0.5 mm

#### RCBUS40 and RCBUS80 bus pins

```none
A15 A14 A13 A12 A11 A10 A9 A8 A7 A6 A5A A4 A3 A2 A1 A0 GND +5V M1 RST CLK INT MRQ IOQ D0 D1 D2 D3 D4 D5 D6 D7 TX RX NU NU NU NU
```

Text Height/Width: 0.5 mm

Note: The 80 pin connector only has the usual 40 pins silkscreened, and next to the wrong row as well! However, there is no space to place correctly, unless place on the rear side?

BP80:

```none
GND  +5v /RFSH  PAGE CLK2 /BUSAK  /HALT /BUSRQ /WAIT /NMI D8 D9 D10 D11 D12 D13 D14 D15 TX2 RX2 USER5 USER6 USER7 USER8
```


Unofficial Backplane-80 Pin-outs

```none
#41 #42 #43 #44 #45 #46 #47 #48 A23 A22 A21 A20 A19 A18 A17 A16 GND  +5v /RFSH  PAGE CLK2 /BUSAK  /HALT /BUSRQ /WAIT /NMI D8 D9 D10 D11 D12 D13 D14 D15 TX2 RX2 USR5 USR6 USR7 USR8
```


#### Jumpers

```none
Switched          16k

Always on         32k

ROM select        ROM size

(P2)              (P1)
```

Text Height/Width: 0.5 mm

#### Squires/GOL Z80 pins

```none
a10 a9 a8 a7 a6 a5 a4 a3 a2 a1 a0 gnd /r /1 /rt /br /w /bq /wr /rd
a11 a12 a13 a14 a15 clk d4 d3 d5 d6 5v d2 d7 d0 d1 /in /n /h /mr /ir
```

Text Height/Width: 0.5 mm

## TODO

 - Rename XTAL to X1 and X2 instead of Y1 and Y2?
   - X1 and X2 renamed Y1 and Y2, as KiCAD auto named
 - Rename Headers and Jumpers? H1 or J1? P1 or J1?
   - P1 and P2 renamed J1 and J2, as they are jumpers
   - H1 and H2 are actually headers, renamed from KiCAD default of J1 and J2
   - J5 and J6 are not jumpers, but connectors to the CH376S board
 - Add ZIF for EEPROM?
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
   - Move all halfway down hole PCBs ina separate directory, as they are redundant and confusing, and cluttering.
 - Need a better naming conventation, it is currently all over the place
 - Add TTL Serial silkscreen (original has this)
 - TTL Serial connector is the wrong way around on Squires, and probably all.
   - My orientation might actually be better:
     - The orientaton of the serial board is matching the orientation of the mother board as the bottom is also facing the bottom, rather than having bare electronics facing down, as in the Squires original.
     - Easier to route, to boot! One less via!
     - Although, it would obscure any "blinken LEDs" on the top side of the serial board
 - The DTR from the serial board is not routed. Is that a problem? In the video [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them
](https://www.youtube.com/watch?v=MaolTlk7XKM) at [1:10](https://www.youtube.com/watch?v=MaolTlk7XKM&t=70), it can be seen that there is a DTR pin on the serial board, and that there "might" be a trace coming fromthe connnector forthat pin, although it is unclear whether it is an joining track. Although DTR is not marked on the front silkscreen for the pins, nor is it in the schematic. TODO: Where on the UART would it go? Which pin? Pin 33, and it goes to the "user" LED.
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
   - GOL has difffering placement from Squires, and RCBUS40 and RCBUS80 board.
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
 - Ensure bycapss caps on ll 4 layr boards, and as best possible on 2 layer (lsit the bad that ill need exernal cap added
 - Put Unofficial Backplane-80 Pin-outs, from [RC2014](https://smallcomputercentral.com/rc2014-bus/specification-rc2014-bus/) on RCBUS80 silkscreen? 
   - No need, extended BP80 pins not wired up.
 - Document the strings used (including spaces) for the pins' labels.
 - Should 8bitstack.co.uk silkscreen be applied?
   - No, as the website is dead
   - Yes, as it maintians authetic feel
   - No, as not having it makes for an easy differentiation that this is a reverse engineeered job.
 - RCBUS variants could route DTR?
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
 - Do bypass capacitor check and make a table/document <--- This!!!
   - Add to candidate table
   - RCBUS40r3ip2z needs a via to add GND to UART
   - If vias are needed then so be it, especially on the lower via count boards, numbering in the 20s.
 - Distance of TTL serial? Check and make table
 - Move up the edge bus on bus80, and gol? Reduce warnings to zero?
 - Remove the needless 61512 files from every board: `Memory_RAM_PC61512.kicad_sym` and `Memory_RAM_UM61512.kicad_sym` and `Memory_RAM_61512.bak` and `Memory_RAM_PC61512.bak`
   - Maybe not, as the symbol editor complains
 - Bring out CTS for RCBUS80
   - Maybe othe variants later
 - RCBUS variants could route CTS?
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



## To do: Things to check on all boards

Ensure:

ROM to the left
RAM not totally to the right
Crytals are shifted left (not down) and close to caps
U5 is on the right edge
HL 5 is correct and not overlapping.
Silkscreen vertical connectors
C7 is close to U7
Silkscreen TTL serial pins (forward) 
Silkscreen TTL serial pins (and reversed) 



## Best board designs

See [PCB Candidates](documentation/Z80%20Playground%20v1.2%20-%20PCB%20candidates.md)

 - RCBUS80r
   - RCBUS80r5cp2fixed3
     - 24 vias
     - DRC OK
 - RCBUS40r
   - 

## Main board variants
 
  - Z80 Playground
    - a replica
  - playgroundZ80
    - a PRO version wih the improvements:
      - capacitors?
      - TTL pin order?
      - CTS?
      - Closer XTAL to UART
      - CPU XTAL not on edge of board?
      - SMD pre-mounted bypass 1 µF caps
      - what else?
  - Z80 PlaygroundRC
    - a replica but with RCBUS40/80
  

<!-- Images -->

  [1]: xtras/hardware/screenshots/v1.2/ebay/Z80%20Playground%20v1.2%20PCB%20and%20components.jpeg "PCB v1.2"
  [2]: xtras/hardware/screenshots/v1.2.1/PCB_and_3DView_RCBUS80r5cp2.png "PCB and 3D image"

  [3]: xtras/hardware/screenshots/TTL_serial_board/Z80PG_TTL_board.png "Z80 Playground TTL serial board"
  [4]: xtras/hardware/screenshots/TTL_serial_board/Red_FTDI_board.png "Red FTDI TTL serial board"
  [5]: xtras/hardware/screenshots/TTL_serial_board/SCD_TTL_board_hi.jpg "TTL serial board as used by Small Computers Direct"

 
