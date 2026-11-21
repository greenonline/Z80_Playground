KiCAD 6 files (schematic, PCB, etc.) for Z80 Playground v1.2 – Coming soon! (End <strike>Aug</strike> <strike>Sept</strike> Dec 2026). 

Delays due to on-going testing – no point in putting out faulty boards!.

Status: Electrically the boards seem to be sound. Silkscreen needs finalising.

Blocking and remaining issues to fix:

 - <strike>Update feature table with C/D/O switches variant</strike>  - **DONE**
 - Add the D/O switch variants to feature table
 - <strike>Tidy the PCB candidates table</strike>  - **DONE**
 - Add the D/O switch variants to PCB candidates table
 - Update website front page
   - include matrix
   - explain boards
   - explain variants
   - archive the "wordy design voyage of discovery" that was the previous front page
 - Add "C" to all existing variant names, for the C&K SMD switch:
   - <strike>folders</strike>                 - **DONE**
   - <strike>pcb sheet</strike>               - **DONE**
   - <strike>schematic sheets</strike>        - **DONE**
   - silkscreen
 - Add "alpha" (until confirmed working) to:
   -  <strike>all boards names</strike> and;  - **DONE**
   -  silkscreens 
 - Finalise silkscreen
 - Apply silkscreen
 - Check discrete component sizes vis-a-vis the footprints, for resistors, capacitors (both ceramic and electrolytic)
 - Add Dual or Omron switches to GOL variants (D/O)
 - Caveats:
   - The CH375S connector *should* be the correct spacing but it might be a tight fit
   - The two layer boards may require external additional bypass caps on the ICs. They shouldn't do, but may require it, experimentation is required...
   - I recommend installing KiCad and opening the PCB files, and maybe the schematics, to do a sanity check, before using the Gerbers
   - I would also recommend purchasing a CH375S yourself and measuring the pin gaps of the two connectors, and verifying these on the PCB, before using the Gerbers.
   - The RCBUS40 4 layer boards do not appear to have filled VCC and GND planes
   - The RCBUS variants will not run RomWBW as is, unless RomWBW is patched. The RAM and ROM would need to be disabled, and (possibly) the USB and UART also
     - The TBA "Pro" version of Z80PG would be compatible w.r.t. the USB and UART as they have fuller addressing and relocatable addresses, via DIP switch. 



