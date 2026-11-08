# Z80 Playground v1.2 - MJ/GOL_ fix for width of 7400 ICs

## Preamble

Design mistake made early in the design, requires rework.

## Notes

`Package_DIP:DIP-14_W10.16mm_LongPads` -> `Package_DIP:DIP-14_W7.62mm_Socket`

### RS2

Z80_Playground (MJ/GOL RS2CPPF) - alignedez4an - 49v - DRC_OK (CTS) copy

alignedez4an -> alignedez4anf

Quite a bit of rework

Z80_Playground (MJ/GOL RS2CUPF) - alignedez4bn - 49v - DRC_OK (CTS) (JMP)

alignedez4bn -> alignedez4bnf

Quite a bit of rework

Z80_Playground (MJ/GOL RS2NPPF) - alignedez4n - 48v - DRC_OK

alignedez4n -> alignedez4nf

Quite a bit of rework

Z80_Playground (MJ/GOL RS2NUPF) - alignedez4jn - 48v - DRC_OK (JMP)

alignedez4jn -> alignedez4jnf

Quite a bit of rework

This was broken, or unfinished, in the original alignedez4jn! The VCC jumper not connected correctly. TODO: Check other NUPF


### RT2

Z80_Playground (MJ/GOL RT2CPPF) - alignedcz4an - 49v - DRC_OK (CTS)

alignedcz4an -> alignedcz4anf

Quite a bit of rework

Z80_Playground (MJ/GOL RT2CUPF) - alignedcz4bn - 49v - DRC_OK (CTS) (JMP)

alignedcz4bn -> alignedcz4bnf

Quite a bit of rework

Z80_Playground (MJ/GOL RT2NPPF) - alignedcz4n - 48v - DRC_OK

alignedcz4n -> alignedcz4nf

Quite a bit of rework

Z80_Playground (MJ/GOL RT2NUPF) - alignedcz4jn - 48v - DRC_OK (JMP)

alignedcz4jn -> alignedcz4jnf

Quite a bit of rework

This was also broken, or unfinished, in the original alignedcz4jn!


### RS4


Z80_Playground (MJ/GOL RS4CPPF) - aligned2pc3zan - 21v - DRC_OK (CTS)

aligned2pc3zan -> aligned2pc3zanf

4 layer was more work than 2 layer! Or maybe I wasn't used to it


Z80_Playground (MJ/GOL RS4CUPF) - aligned2pc3zbn - 21v - DRC_OK (CTS) (JMP)

aligned2pc3zbn -> aligned2pc3zbnf

Z80_Playground (MJ/GOL RS4NPPF) - aligned2pc3zn - 21v - DRC_OK

aligned2pc3zn -> aligned2pc3znf

Z80_Playground (MJ/GOL RS4NUPF) - aligned2pc3znj - 21v - DRC_OK (JMP)

aligned2pc3znj -> aligned2pc3znjf

Actaully, it is n't that bad. Maybe easier than 2 layer.


### RT4

Z80_Playground (MJ/GOL RT4CPPF) - aligned2pc2zan - 21v - DRC_OK (CTS)

aligned2pc2zan -> aligned2pc2zanf

Lots of GND fixes required (15-20?) Was the original the same??? Unfinished? No, the original aligned2pc2zan was fine. Very strange.


Z80_Playground (MJ/GOL RT4CUPF) - aligned2pc2zbn - 21v - DRC_OK (CTS) (JMP)

aligned2pc2zbn -> aligned2pc2zbnf

Much easier, and no GND issues! Odder still!



Z80_Playground (MJ/GOL RT4NPPF) - aligned2pc2zn - 21v - DRC_OK

aligned2pc2zn -> aligned2pc2znf

Much easier, and no GND issues! Odder still!

Z80_Playground (MJ/GOL RT4NUPF) - aligned2pc2zjn - 21v - DRC_OK (JMP)

aligned2pc2zjn -> aligned2pc2zjnf

Much easier, and no GND issues! Odder still!
