# Thermostat (0005)

A thermostat indicating too _low/OK/to high_ temperature with LEDS.

## Description

This circuit is a copy of [AVT-1742](./AVT1742.pdf) converted to Surface Mounted Technology.

<img src="images/schematic.png" alt="Schematic" style="width:600px;"/>

## Assembly

This circuit should be assembled on a double-sided, SMT printed circuit board.

<img src="images/pcb_front.png" alt="PCB front layout" style="width:600px;"/>

<img src="images/pcb_back.png" alt="PCB back layout" style="width:600px;"/>

## Running

The device should be powered with 12DCV connected to J3 junction (mind the polarization).

Comparing to the original solution, either a thermistor embedded into the PCB or the external thermistor connected to
junction J1 can be used. Jumper JP1 should be soldered when the embedded thermistor is used, or de-soldered when the
external thermistor is used.

The high/lowh temperature thresholds should be calibrated using potentiometers P1 and P2, or external potentiometers
connected to J5 and J6. Jumper JP2 should be soldered when the embedded potentiometers are used, or de-soldered when the
external potentiometers are used.

The thresholds (low/ok/high) are presented with LED1 (high), LED2 (OK) and LED3 (low), or external LEDs connected to
junction J4 (LED current limiting resistors are required, open-collector outputs). Jumper JP3 should be soldered when
the embedded LEDs are used, or de-soldered when the embedded LEDs are not used.

The thresholds can be used to trigger external devices (e.g. using relays). External devices should be connected to
junction J2 (coil current limiting resistors are required, open-collector outputs; the current should be <80mA -
limitation of BC847B transistor; recommended current <40mA, as it's possible that two signals are enabled due to
incorrect calibration).

## Bill of materials

| Reference   | Qty | Value    | Footprint             |
|:------------|:----|:---------|:----------------------|
| C1,C2,C4,C5 | 4   | 100nF    | 0603                  |
| C3          | 1   | 470uF    | Electrolytic D=10mm   |
| D1,D2,D3    | 3   | 1N4148   | SOD-323               |
| J1          | 1   | EXT\_NTC | JST-SH 1x2 Vertical   |
| J2          | 1   | OUT      | JST-SH 1x4 Vertical   |
| J3          | 1   | PWR      | JST-SH 1x2 Vertical   |
| J4          | 1   | EXT\_LED | JST-SH 1x4 Vertical   |
| J5          | 1   | EXT\_P1  | JST-SH 1x3 Vertical   |
| J6          | 1   | EXT\_P2  | JST-SH 1x3 Vertical   |
| LED1        | 1   | RED      | 0603                  |
| LED2        | 1   | GREEN    | 0603                  |
| LED3        | 1   | BLUE     | 0603                  |
| NTC1        | 1   | 22k      | 0603                  |
| P1,P2       | 2   | 22k      | Bourns_3224W_Vertical |
| R1,R2,R3    | 3   | 10k      | 0603                  |
| R4,R5       | 2   | 1M       | 0603                  |
| R6,R7       | 2   | 2,2k     | 0603                  |
| R8,R9,R10   | 3   | 15k      | 0603                  |
| R11,R12,R13 | 3   | 1k       | 0603                  |
| T1,T2,T3    | 3   | BC847B   | SOT-23                |
| US1         | 1   | LM393    | DFN-8-1EP             |
| US2         | 1   | 4011     | TSSOP-14              |
