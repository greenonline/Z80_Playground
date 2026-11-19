KiCAD 6 files (schematic, PCB, etc.) for Z80 Playground v1.2 – Coming soon! (End <strike>Aug</strike> Sept 2026). 

Delays due to on-going testing – no point in putting out faulty boards!.

Status: Electrically the boards seem to be sound. Silkscreen needs finalising.

Blocking and remaining issues to fix:

 - Update feature table/matrix with C/D/O switches variant
 - Update website front page
   - include matrix
   - explain boards
   - explain variants
   - archive the "wordy design voyage of discovery" that was the previous front page
 - Add "C" to all existing variant names, for the C&K SMD switch:
   - folders
   - pcb sheet
   - schematic sheets
   - silkscreen
 - Add "alpha" to all boards names and silkscreens until confirmed working
 - Finalise silkscreen
 - Apply silkscreen
 - Check discrete component sizes vis-a-vis the footprints, for resistors, capacitors (both ceramic and electrolytic)
 - Add Dual or Omron switches to GOL variants (D/O)
 - Caveats:
   - The CH375S connector *should* be the correct spacing but it might be a tight fit
   - The two layer boards may require external additional bypass caps on the ICs. They shouldn't do, but may require it, experimentation...
   - I recommend installing KiCad and opening the PCB files, and maybe the schematics, to do a sanity check, before using the Gerbers
   - I would also recommend purchasing a CH375S yourself and measuring the pin gaps of the two connectors, and verifying these on the PCB, before using the Gerbers.



