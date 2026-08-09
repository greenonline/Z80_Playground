# Z80 Playground v1.2 - footprints 

## Preamble

The component footprints for the Z80 Playground v1.2 layout, as derived from the images shown in the video, [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them](https://www.youtube.com/watch?v=MaolTlk7XKM).

## Notes

### Footprints used

#### MJ/GOL variant

This was the first PCB layout attempt. The footprints used are listed below.

Capacitors:

 - `C1` 10 µF: `Capacitor_THT:CP_Radial_D5.0mm_P2.50mm`
 - `C2` 1 µF: `Capacitor_THT:CP_Radial_D5.0mm_P2.00mm`
 - `C8` 47 µF: `Capacitor_THT:CP_Radial_D6.3mm_P2.50mm`
 - `C13` 100 nF: `Capacitor_THT:C_Disc_D5.1mm_W3.2mm_P5.00mm`
 - `C9` 100 nF: `Capacitor_THT:C_Disc_D5.1mm_W3.2mm_P5.00mm`
 - `C17` 47 pF: `Capacitor_THT:C_Disc_D3.8mm_W2.6mm_P2.50mm`
 - `C18` 22 pF: `Capacitor_THT:C_Disc_D3.8mm_W2.6mm_P2.50mm`
 - `C5` 8 pF: `Capacitor_THT:C_Disc_D3.8mm_W2.6mm_P2.50mm`
 - `C6` 8 pF: `Capacitor_THT:C_Disc_D3.8mm_W2.6mm_P2.50mm`
 - Maybe for `C5` and `C6` 8 pF (RCBUS): `Capacitor_THT:C_Disc_D3.0mm_W2.0mm_P2.50mm`

Resistors:

 - `R8` 10k: `Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal`
 - Vertical: `Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P2.54mm_Vertical`

XTAL

 - `Y1`: `Crystal:Crystal_HC49-4H_Vertical`

Switch

 - `SW1`: `Button_Switch_SMD:SW_SPST_CK_RS282G05A3`
 - Also possible: `Button_Switch_SMD:SW_Tactile_SPST_NO_Straight_CK_PTS636Sx25SMTRLFS`
 - OMRON: `???`

Headers

 - `H1`: `Connector_PinHeader_2.54mm:PinHeader_1x06_P2.54mm_Horizontal`
 - `H2`: was `My_Components:Conn_Pin_Header_39x1_2.54mm`, now `Connector_PinHeader_2.54mm:PinHeader_1x39_P2.54mm_Horizontal`
 - `H3` (RCBUS): `Connector_PinHeader_2.54mm:PinHeader_1x10_P2.54mm_Horizontal`
 - `H4` (RCBUS): `Connector_PinHeader_2.54mm:PinHeader_1x05_P2.54mm_Horizontal`

Jumpers:

 - `J1`: `Connector_PinHeader_2.54mm:PinHeader_1x03_P2.54mm_Vertical`
 - `J2`: `Connector_PinHeader_2.54mm:PinHeader_1x03_P2.54mm_Vertical`
 - `J5`: `Connector_PinSocket_2.54mm:PinSocket_2x03_P2.54mm_Vertical`
 - `J6`: `Connector_PinSocket_2.54mm:PinSocket_2x08_P2.54mm_Vertical`

LED:

 - `LED1`: `LED_THT:LED_D3.0mm`

IC:

 - `U8` (GOL): `Package_DIP:DIP-14_W7.62mm_LongPads`
 - `U5` (Squires): `Package_DIP:DIP-14_W7.62mm`
 - `U6` (Squires): `Package_DIP:DIP-14_W7.62mm`
 - `U7` (Squires): `Package_DIP:DIP-14_W7.62mm`
 - `U8` (Squires): `Package_DIP:DIP-14_W7.62mm`
 - `U8` (RCBUS): `Package_DIP:DIP-14_W7.62mm`
