# Z80 Playground v1.2 - Front and rear side annotations

## Notes

### Board identifier

Placement: 

 - Bottom right?
 - Top left?
 - Underside (stay clear of daughter boards)

The board's identifier consists of two parts:

 - Project version
 - Board variant code

The version number pertains more to the schematic, and the board variant code pertains more to the PCB layout.

The version number of 1.2.1 was chosen to reflect the fact that while the schematic diagram is *essentially the same as the Squires version 1.2*, there may be differences in the schematic that I am unaware of. 

This is because the files pertaining to that design no longer exist, and so this is, unavoidably so, a different version as it has been recreated as best possible, given the limited documentation (as well as the obvious routing differences on the PCB). However, the routing differences, of the subsequent board variations, are not reflected in the version number, but instead by a six letter description of the base PCB layout followed by a five character code for the three minor variations of that layout.

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
   - C/N - CTS is exposed, or not
   - U/P - VCC is jumpered, or not
   - P/N - Positive or negative edge triggered NMI
   - F/S - Fixed or Switchable RAM
    
Note: No front mounted bus boards have been published, due to excessive number of vias arising through routing, so the `R` is effectively redundant, seeing as *all* of the published boards have reverse mounted buses. Thus, the `F` actually *is* redundant.

Date, Project, version, board variant code:

```none
Aug 2026, Z80 Playground v1.2.1 ([SQUIRES|MJ_GOL_|RCBUS40|RCBUS80][R|F][T|S][2|4][C|N][U|P][N|P][F|S])
```

So, for example, for Squires board, with reversed bus, TTL orientation, 4 layer, CTS exposed, a jumpered VCC, and positive edge triggered NMI:

```none
Aug 2026, Z80 Playground v1.2.1 (SQUIRESRT4CUPF)
```

An original Squires would be with reversed bus, Squires orientation, 4 layer, CTS not exposed, no jumpered VCC, and positive edge triggered NMI (and a fixed RAM)

```none
Aug 2026, Z80 Playground v1.2.1 (SQUIRESRS4NPPF)
```


### Github URL

Placement:

 - Bottom left? 
 - Or across the board in big 8bitstack.co.uk style?
   - Yes!!! No

### Squires/GOL bus pins

```none
VCC 0v /re /wa /bk /bq /1 nm /rd /wr /mr /io a15 a14 a13 a12 a11 a10 a9 a8 a7 a6 a5 a4 a3 a2 a1 a0 d7 d6 d5 d4 d3 d2 d1 d0
```

Text Height/Width: 0.5 mm

### RCBUS40 and RCBUS80 bus pins

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


### Jumpers

```none
Switched          16k

Always on         32k

ROM select        ROM size

(P2)              (P1)
```

Text Height/Width: 0.5 mm

### Squires/GOL Z80 pins

```none
a10 a9 a8 a7 a6 a5 a4 a3 a2 a1 a0 gnd /r /1 /rt /br /w /bq /wr /rd
a11 a12 a13 a14 a15 clk d4 d3 d5 d6 5v d2 d7 d0 d1 /in /n /h /mr /ir
```

Text Height/Width: 0.5 mm

### Logos

#### "Z80 Playground"

KiCad 6 does not offer stylised text.

Size: 2.5x2.5x0.3

#### RCBUS

A previously designed "RCBUS" logo can be seen in this image from [this image](https://image.easyeda.com/pullimage/EJWyMbsD7FQs4Te0AyXktCU9bAuZ2KYBkX3WZGBh.jpeg) from [SC706 v1.0 Z80 CPU](https://oshwlab.com/sccousins/sc706-v1-0-z80-cpu-for-rcbus)

[![RCBUS logo][6]][6]

[![RCBUS logo][7]][7]

Two alternatives:

 - Standard KiCad 6 font, italics, 1.5x1.5x0.375
 - Impact font, 144pt, and create/import an SVG graphic and scale.


The size of the Impact font, in:

 - macSVG:
   - Impact 144
   - 150 x 400 px
 - Inkscape:
   - Also around 150 x 400 px (389.637, 126.391) (280.742, 118.617)

From [How to Convert SVG to PNG on Mac? Preview App Can't Open SVG](https://discussions.apple.com/thread/255717253) (meh, use Inkscape?)

```none
/usr/bin/sips -s format png -o RCBUS_logo_impact.png RCBUS_logo_impact.svg
```

Making this logo in SVG format, on a Mac was rather tricky, and I am not alone. See [Exporting Sketch as SVG cannot be imported in KiCad PCB Editor](https://forum.freecad.org/viewtopic.php?t=74596). Initially, I managed to get a blank rectangle (presumably the background) when created in **macSVG**, but then removing the background reverted back to the "no graphics" error in KiCAD:

[![KiCAD6 No graphic items error][8]][8]

#### Things that do not work (in Inkscape)

 - The menu item  **Edit>Make a Bitmap Copy**, in Inkscape, didn't seem to help either. Create bitmap and copy and paste into new Inkscape doc, nope!
 - Alternative from [Custom Fonts in KiCad?](https://forum.kicad.info/t/custom-fonts-in-kicad/9438/3) is [svg2mod](https://github.com/mtl/svg2mod)

    > uncompressed Inkscape SVG (i.e., not "plain SVG") format

 - Changing the size of the canvas in Inkscape did not change the size of the imported white rectangle in KiCAD.
 - Opening the layers and objects and removing everything except for the bitmap of the text, didn't help
 - Saving as every `.svg` file type: Inkscape, plain, optimised, - no help either.
 - Changing the transparency (opacity of background to 0%), of the background image in Inkscape, still imported white rectangle.

#### HOW-TO - method 1

To create "RCBUS" stylised text logo.

Using:

 - Inkscape v1.2
 - macSVG 1.2
 - OSX Catalina

Step 9 is the important step:

1. Create the text in macSVG
   - Text: "RCBUS"
   - Font: Impact
   - Size 144
2. Save
3. Open in Inkscape
4. **Object>Layer and Objects**
5. Open `main_group` directory
6. Delete the background rect
7. Select the text
8. **Edit>Resize Page to Selection**
9. **Path>Object to Path** ( or **Path>Stroke to Path**, both are the same)
10. Save (or, As... > SVG: Inkscape or Plain)
11. Import into KiCad, Import scale 0.075

Results:

 - Working file: `image11i2b.svg` (Stroke to Object - saved as Inkscape SVG)
 - Working file: `image11i2c.svg` (Stroke to Path - saved as Plain SVG)
 - Working file: `image11i2d.svg` (Stroke to Object - saved as Plain SVG)

Import scale: 0.075 (to match scale of native text: Italics, 1.5x1.5x0.375)

#### HOW-TO - method 2

To create "ZPG" (and "Z80PG") stylised text logo.

Using:

 - macSVG 1.2
 - OSX Catalina


1. Open macSVG
2. Uncheck "Include background rect"
3. Click Create New Document
4. Select the "Sample Text Element" and delete
5. **Plug-ins>>Path Text Generator**
   - Text "ZPG"
   - Font: Optima-ExtraBlack
   - Size: 144
6. Click **Generate Path** button
7. Save (or, As... > SVG: Inkscape or Plain)
8. Import into KiCad, Import scale 0.1.
 
#### Open source hardware logo

 - Source: [Open source hardware logo](https://github.com/OSHW/logo) 
   - `oshw_logo.svg` - the whole logo, Import scale : 0.1
   - `disegno.svg` - just the "cog", Import scale : 0.01


#### KiCAD logo

 - Source: [Wikipedia](https://commons.wikimedia.org/wiki/File:KiCad-Logo.svg)
   - Import scale : 0.1

##### "Designed with KiCAD" logo

Meh, these "Designed with" logos are all overblown and blurry. Any attempt to sharpen and redraw paths fails, [Where is the KiCad monotone logo of svg file and DESIGNED WITH?](https://forum.kicad.info/t/where-is-the-kicad-monotone-logo-of-svg-file-and-designed-with/8838).



#### IC logo

Created in KiCad, after importing the SVG from [integrated-circuit](https://freesvg.org/integrated-circuit), and tracing outline.

Then take a PNG screenshot, of the image in KiCad, remembering to turn off the grid. Then open in Inkscape, and transform into a path (and invert). Then reimport back into KiCad.

##### Adding "ZPG" to the IC

Open both the "straight" text, and IC logo in Inkscape. Copy the text and paste onto the IC.

There are two methods to shear:

 - Shearing of the paths (not the image) in Inkscape and adjusting size, can be done using the basic selection handles. I just ended up doing it by eye. No reproducible steps – a one time shot only.

 - There may be no need for **Path>Path Effects...**> + > **Perspective/Envelope** – If you put in the co-ords of the IC surface corners, then the text shears appropriately. Unfortunately, the sheared text is not *on* the IC but to the side, and refuses to be moved [Ed. - the second time I was able to move and place the text]. However, if you then copy (or cut) the text from the IC Logo file, into a new file, and **Edit>Resize Page to Selection**, save. Then copy this image (slanted text) back to the IC logo and move into position.

   Therefore, a more reproducible method of creating the "slant":

    - IC corner co-ords:
      - Top Left: (162,458) +X
      - Bottom Left: (400,593) -Y
      - Top Right: (922,16) +Y
      - Bottom Right: (1160,154) -X
 
   Note: Need to indent by 10(?) pixels to fix properly. But not x *and* y
   
    - IC corner co-ords:
      - Top Left: (172,458) +X
      - Bottom Left: (400,583) -Y
      - Top Right: (922,26) +Y
      - Bottom Right: (1150,154) -X
 
   Perfect result! Bold and stands out.
   
I ended up making a lot of logos:

 - ICZPG
 - ICZ80PG
 - ICZ80Playground
 - ICZilogPlayground logo
 - ICZ180PG logo
 - ICZ180Playground logo
 
However, there was a mark on the original IC logo PNG screenshot, maybe of the KiCad cursor.

New file: IC_logo.svg

New coords of corners:

    - IC corner co-ords:
      - Top Left: (3,118) +X
      - Bottom Left: (66,155) -Y
      - Top Right: (204,2) +Y
      - Bottom Right: (267,38) -X

New coords of indented corners + 10:

    - IC corner co-ords:
      - Top Left: (13,118) +X
      - Bottom Left: (66,145) -Y
      - Top Right: (204,12) +Y
      - Bottom Right: (257,38) -X

Note that the co-ords are much lower. This results in the text being oriented correctly, but much too small. Not clear why resolution is lower (import default resolution?) – except for Z180PG which is resized perfectly 

However, (**Object>Transform...**) scaling up by 375%, both width and height, fixes it (400% made it oversized for the IC surface) (Use 375% more or less, maybe use more than 375%)


#### Reversing the logos

The KiCad, OSHW, RCBUS and ZPG logos should be mirrored and placed on the rear silkscreen, as KiCad 6 can not mirror graphics, even though it *can* mirror text.

Do this using Inkscape, with the **Object>Flip Horizontal** menu, and save and import into KiCad.



<!-- Images -->

  [6]: https://image.easyeda.com/pullimage/EJWyMbsD7FQs4Te0AyXktCU9bAuZ2KYBkX3WZGBh.jpeg "RCBUS logo"
  [7]: ../xtras/hardware/screenshots/RCBUS/RCBUS_logo_SC706_crop.jpeg "RCBUS logo"
  [8]: ../xtras/hardware/screenshots/RCBUS/KiCAD6_No_graphic_items.png "KiCAD6 No graphic items error"

