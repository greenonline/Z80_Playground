# Z80 Playground v1.2 - serial/power module

Dimensions (red FTDI): 18 x 36 mm

Not sure that I like the idea of possible shorts – Use captan tape for protection and sticky foam pad for spacing.

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

However, for the more usual cloned red FTDI module, with the board component side up, the connnections are in the reverse order..!

[![Red FTDI TTL serial board][4]][4]

```none
 GND  RTS  VCC   RX   TX
```

Of course, one could flip the TTL serial board over in order to realign the pins in the correct order, but then the blinken lights would be obscurred, as they would be facing the undersie of the motherboard. It all depends upon whether you believe that the correct orientation for a *daughter board, mounted beneath the motherboard*<sup>*</sup>, should have its components facing down, or up. In other words, should the underside of the completed unit show only PCB undersides, or, more inconsistantly, the motherboard underside and the TTL serial board's front side? In my mind, the latter is not dissimilar to serving a quiche upside down on a plate.

Nevertheless, one thing should be clear, these TTL boards with the DTR line exposed are actually *intended for uploading sketches to Arduinos*. For full-handshaking, the TTL serial board should have CTS and RTS available, and not DTR.

The more correct TTL serial board used by Small Commputers Central is:

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

<sup>*</sup> IMHO, the underside is the worst possible orientation for a daughter board. Daughter boards should really mount to the front of a board. However, in this limited-real-estate case, it is understandable why it was done in this manner. The motherboard's own LEDs would be covered by a front mounting daughter board, if the TTL connector were to remain in the same location.

