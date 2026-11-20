# Z80 Playground v1.2 - Switches

There are three PCB variants for the switches, denoted by the code: `C/D/O`.

The original design used [C&K SMB switches](https://www.digikey.com/en/products/detail/c-k/RS-282G05A3-SM-RT/2747190) - these are the `C` variants.

Footprint: `Button_Switch_SMD:SW_SPST_CK_RS282G05A3`

However, I would rather use through-hole Omron 12 mm or 6 mm momentary switches (as I have a lot of these lying around):

Footprints:

 - 6 mm `Button_Switch_THT:SW_TH_Tactile_Omron_B3F-10xx`
   - 6 mm equivalent: `Button_Switch_THT:SW_PUSH_6mm`
 - 12 mm `Button_Switch_THT:SW_PUSH-12mm`


However, the 12 mm switches are way too large for this small board and take up too much space. However, the 6 mm Omron witches fit just fine.

I have attempted to provide *dual* switch footprints that support both Omron and C&K switches – this are the `D` variant.

However, in some cases this was not possible, and Omron only footprints are used instead - this are the `O` variant


### Rough notes, taken from TODO

Taken from [Z80 Playground v1.2 - TODO](Z80%20Playground%20v1.2%20-%20TODO.md)

 - Make version/variant with OMRON buttons
   - Add OMROM to all boards at the same time.
   - 12 x 7.3 mm
   - `Button_Switch_THT:SW_PUSH-12mm`
     - huge! and pins seem too close together
       - not enough room!
     - or same `Button_Switch_THT:SW_PUSH-12mm_Wuerth-430476085716`
       - huge!
         - not enough room!
   - or `Button_Switch_THT:SW_TH_Tactile_Omron_B3F-10xx`
     - nice size
     - or same `Button_Switch_THT:SW_PUSH_6mm`
       - nice size
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


### Implentation docs

 - [Z80 Playground v1.2 - Adding 6 mm OMRON momentary buttons](Z80%20Playground%20v1.2%20-%20Adding%206%20mm%20OMRON%20momentary%20buttons.md)