# Z80 Playground v1.2 - parts list 

## Preamble

The component footprints for the Z80 Playground v1.2 layout, as derived from the images shown in the video, [Z80 playground v1.2 - The Z80 Single Board Computer - How to install CP/M programs and run them](https://www.youtube.com/watch?v=MaolTlk7XKM).

## Notes

Note: This following table is deprecated by the next expanded table down.

| Part    | Qty | Description                            |
|---------|-----|----------------------------------------|
| IC      | 8   | IC        total                        |
| Z80     | 1   | CPU                                    |
| 61512   | 1   | RAM                                    |
| 28C256  | 1   | EEPROM                                 |
| 16C550  | 1   | UART                                   |
| 74HC02  | 1   | NOR                                    |
| 74HC32  | 2   | OR                                     |
| 74HC14  | 1   | NOT                                    |
| Switch  | 3   | Push button                            |
| LED     | 5   | Power, user, halt, rom, disk           |
| R       | 14  | Resistor  total                        |
| 470R    | 1   | Resistor  - CPU clock                  |
| 1k      | 5   | Resistor  - LED                        |
| 1k5     | 1   | Resistor  - UART clock                 |
| 10k     | 6   | Resistor  - Pull down (3), pull up (3) |
| 1M      | 1   | Resistor  - CPU clock                  |
| C       | 13  | Capacitor total                        |
| 8 pF    | 2   | Capacitor - CPU Crystal                |
| 22 pF   | 1   | Capacitor - UART Crytal                |
| 47 pF   | 1   | Capacitor - UART Crytal                |
| 100 nF  | 8   | Capacitor - Decoupling                 |
| 1 µF    | 1   | Capacitor - Interrupt                  |
| 10 µF   | 1   | Capacitor - Reset                      |
| 47 µF   | 1   | Capacitor - Power                      |
| Header  | 6   | Header total                           |
| 1x03    | 2   | Header, J1 and J2                      |
| 1x06    | 1   | Header, TTL Serial, H1                 |
| 2x03    | 1   | USB1                                   |
| 2x08    | 1   | USB2                                   |
| 1x36    | 1   | Edge connector, H2 (optional)          |
| 1x40    | 1   | Edge connector, H2 (optional)          |
| CH376S  | 1   | USB module                             |
| FTDI    | 1   | USB to TTL serial                      |

Note: Three capacitors, C14-C16, are not present in the schematic.

A more complete table, showing component IDs:

| ID                | Part    | Qty | Description                            |
|-------------------|---------|-----|----------------------------------------|
| ----------------- | IC      | 8   | IC        total                        |
| U1                | Z80     | 1   | CPU                                    |
| U2                | 61512   | 1   | RAM                                    |
| U3                | 28C256  | 1   | EEPROM                                 |
| U11               | 16C550  | 1   | UART                                   |
| U8                | 74HC02  | 1   | NOR                                    |
| U5,6              | 74HC32  | 2   | OR                                     |
| U7                | 74HC14  | 1   | NOT                                    |
| ----------------- | R       | 14  | Resistor  total                        |
| R6                | 470R    | 1   | Resistor  - CPU clock                  |
| R1-3, R10, R16    | 1k      | 5   | Resistor  - LED                        |
| R7                | 1k5     | 1   | Resistor  - UART clock                 |
| R4, R8-9, R13-15  | 10k     | 6   | Resistor  - Pull down (3), pull up (3) |
| R5                | 1M      | 1   | Resistor  - CPU clock                  |
| ----------------- | C       | 15  | Capacitor total                        |
| C5,6              | 8 pF    | 2   | Capacitor - CPU Crystal                |
| C18               | 22 pF   | 1   | Capacitor - UART Crytal                |
| C17               | 47 pF   | 1   | Capacitor - UART Crytal                |
| C3-4, C7-13       | 100 nF  | 8   | Capacitor - Decoupling                 |
| C2                | 1 µF    | 1   | Capacitor - Interrupt                  |
| C1                | 10 µF   | 1   | Capacitor - Reset                      |
| C8                | 47 µF   | 1   | Capacitor - Power                      |
| ----------------- | Header  | 6   | Header total                           |
| J1, J2 (P1, P2)   | 1x03    | 2   | Header, J1 and J2                      |
| H1                | 1x06    | 1   | Header, TTL Serial, H1                 |
| J5     (U10)      | 2x03    | 1   | USB1                                   |
| J6     (U10)      | 2x08    | 1   | USB2                                   |
| H2                | 1x36    | 1   | Edge connector, H2 (optional)          |
| H2                | 1x40    | 1   | Edge connector, H2 (optional)          |
| ----------------- | Switch  | 3   | Switch total                           |
| SW1-3             | Switch  | 3   | Push button                            |
| ----------------- | LED     | 5   | LED total                              |
| LED1-5            | LED     | 5   | Power, user, halt, rom, disk           |
| ----------------- | Other   | 2   | Other total                            |
| U10               | CH376S  | 1   | USB module                             |
| TTL serial        | FTDI    | 1   | USB to TTL serial                      |

