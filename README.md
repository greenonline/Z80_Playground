# Z80_Playground
A repo containing info for the Z80 SBC, designed by John Squires

# Z80_Playground

Or [PlaygroundZ80](https://github.com/greenonline/playgroundZ80)!!!

## Preamble

John Squires, of the now defunt [8bitstack.co.uk](https://8bitstack.co.uk), and the YouTube channel, [John Squires](https://www.youtube.com/@CircuitBreaker256), created a very nifty Z80 SBC that could run CP/M and Tiny BASIC, amongst other things.

Unfortunately, around 2022, new videos ceased to be posted, and the whole project seemed to have died.

There don't appear to be any parts lists, schematics, PCB layouts, gerber files – basically, there seems to be little in the way of hardward documentationb, apart from the videos. However, there are still Github repos for the software, that are still up, so that is good.

Using the Wayback machine I managed to get hold of some PDFs of the schematics for v1.1 and v.1.2, and some additional software, see the section **Wayback data** below.

From these schematic diagrams, using KiCAD 6, I managed to recreate the schematics and the PCB, for v1.2.

I reused, where I could, the Squires 'forward-slash-and-lowercase-camelcase' type of annotation – even though it feels rather inconsistant and messy/awkward.

I also made two other variants: a (IMHO) better annotated version (`GOL`, AKA `MJ`, variant), using a a shorter (more standard) 'uppercase-and-underscore' form of annotation., and; a version using an RC2014 Extended bus (`RCBUS` variant), that should make the board a bit more useful, *if* you so happen to have an RC2014 lying around – see [playgroundZ80](https://github.com/greenonline/playgroundZ80).

There is also my initial attempt, that has two styles of annotation: the Squires 'forward-slash-and-lowercase-camelcase' type and a shorter (more standard) 'uppercase-and-underscore' form of annotation. This is the `dual version` variant.

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

### Wayback data

Information and data recovered from the Wayback machine, included in *this* repo:

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

 - R8 10k: `Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal`

XTAL

 - Y1 :`Crystal:Crystal_HC49-4H_Vertical`

Switch

 - SW1: `Button_Switch_SMD:SW_SPST_CK_RS282G05A3`
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



## TODO

 - Rename XTAL to X1 and X2 instead of Y1 and Y2?
 - Rename Headers and Jumpers? H1 or J1?
