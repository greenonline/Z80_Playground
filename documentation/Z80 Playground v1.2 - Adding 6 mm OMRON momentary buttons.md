# Z80 Playground v1.2 - Adding 6 mm OMRON momentary buttons

## Notes

 - Make version with OMRON buttons
   - Add OMROM to all boards at the same time.
   - 12 x 7.3 mm
   - `Button_Switch_THT:SW_PUSH-12mm`
     - huge! and pins seem too close together
       - not enough room!
     - or same `Button_Switch_THT:SW_PUSH-12mm_Wuerth-430476085716`
       - huge!
         - not enough room! 3us->3uu
   - or `Button_Switch_THT:SW_TH_Tactile_Omron_B3F-10xx`
     - nice size
     - or same `Button_Switch_THT:SW_PUSH_6mm`
       - nice size! 3us->3uu
       - Much more doable: `RT4CUNSSSO`, reduced -2 vias!
   - Make dual footprint, of `Button_Switch_SMD:SW_SPST_CK_RS282G05A3` and `Button_Switch_THT:SW_PUSH_6mm`
     - `Button_Switch_SMD:SW_SPST_CK_RS282G05A3_OMRON6`
     - Project library: `DualSMD_OMRON_Library:SW_SPST_CK_RS282G05A3_PUSH_6mm`
     - Create new library
     - Create new footprint
     - Paste in `Button_Switch_SMD:SW_SPST_CK_RS282G05A3`
     - Paste in `Button_Switch_THT:SW_PUSH_6mm`
     - Rotate 90° anti-clock
     - Center
     - Remove any silkscreen lines over solder pads
     - The REF*** has to match the THT or SMD setting, but pads can be either SMD or THT

## Routing
### OMron 12 mm only

Notes: `...3us` -> `...3ut`

#### RCBUS80

Z80_Playground (RCBUS80 RT4CUNSSS) - RCBUS80r5cp2fixed3zbo3us - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix: RCBUS80r5cp2fixed3zbo3ut (CUNSSSO)

#### RCBUS40

Z80_Playground (RCBUS40 RT2CUPSSS) - (RCBUS40r3iz7b3us) - 56v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3iz7b3ut (CUPSSSO)

Not done, 12 mm buttons too big

Z80_Playground (RCBUS40 RS2CUPSSS) -  (RCBUS40r3jz7b3us) - 56v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3jz7b3ut (CUPSSSO)

Not even created directory – no point as 12 mm is too big

### Omron 6 mm only

Note: `...3us` -> `...3uu`

Some via reduction due to the removal of those irritating SMD buttons

#### RCBUS80

Z80_Playground (RCBUS80 RT4CUNSSS) - RCBUS80r5cp2fixed3zbo3us - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix: RCBUS80r5cp2fixed3zbo3uu  (CUNSSSO)

-2 via!

#### RCBUS40

Z80_Playground (RCBUS40 RT2CUPSSS) - (RCBUS40r3iz7b3us) - 56v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3iz7b3uu (CUPSSSO)

Done, not too bad. Way better than the dual button footprint.

-1 via! RESET

Z80_Playground (RCBUS40 RS2CUPSSS) -  (RCBUS40r3jz7b3us) - 56v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3jz7b3uu (CUPSSSO)

Done, not too bad. Way better than the dual button footprint.

-1 via! RESET


### Combined Push 6 mm and SMD button Boards

Note: `...3us` -> `...3ud`

#### RCBUS80

Z80_Playground (RCBUS80 RS2CUNSSS) - RCBUS80r5gz9bp3us - 65v - DRC_OK (CTS) (JMP)

Fix: RCBUS80r5gz9bp3ud (CUNSSSD)

-1 via! for /INT = 64
-1 via for NMI = 63

Z80_Playground (RCBUS80 RS4CUNSSS) - RCBUS80r5cp2fixed4zbm3us - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix: RCBUS80r5cp2fixed4zbm3ud (CUNSSSD)

Z80_Playground (RCBUS80 RT2CUNSSS) - RCBUS80r5fz9bp3us - 65v - DRC_OK (CTS) (JMP)

Fix: RCBUS80r5fz9bp3ud (CUNSSSD)

-1 via! for /INT = 64
-1 via for NMI = 63

Z80_Playground (RCBUS80 RT4CUNSSS) - RCBUS80r5cp2fixed3zbo3us - 25>24v - HL5_FIXED, DRC_OK (CTS) (JMP)

Fix: RCBUS80r5cp2fixed3zbo3ud (CUNSSSD)

#### RCBUS40


Z80_Playground (RCBUS40 RS4CUPSSS) - (RCBUS40r3ip2z2b3us) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ip2z2b3ud (CUPSSSD)

Z80_Playground (RCBUS40 RT4CUPSSS) - (RCBUS40r3ipz2b3us) - 21>20v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3ipz2b3ud (CUPSSSD)

Z80_Playground (RCBUS40 RT2CUPSSS) - (RCBUS40r3iz7b3us) - 56v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3iz7b3ud (CUPSSSD)

Difficult, too many tracks where the OMROM through holes are.

Switches need to move up, or RAM move down.

It is a real mess, tracks need to be rerouted all around, long traces. The problem is the combination of the the buttons makes it hard to route around or between the pins and pads. OMRON alone would be more possible to route.

TODO...

Z80_Playground (RCBUS40 RS2CUPSSS) -  (RCBUS40r3jz7b3us) - 56v - DRC_OK (CTS) (JMP)

Fix: RCBUS40r3jz7b3ud (CUPSSSD)

Difficult, too many tracks where the OMROM through holes are.

Switches need to move up, or RAM move down.

It is a real mess, tracks need to be rerouted all around, long traces. The problem is the combination of the the buttons makes it hard to route around or between the pins and pads. OMRON alone would be more possible to route.

TODO...



