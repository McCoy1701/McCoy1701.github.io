
## 65c02 Workbench Computer

The main goal of this project is to facilitate my needs to program EEPROMs, control external peripherals using SPI, I2C, and over UART, drive
other miscellaneous logic devices, control servos with PWM.

The cpu is a WDC 65c02 running at 1 MHz. With a AS6C62256 32k x 8bit static ram; the system only uses 16k for the main ram. It has one 65c22
Versatile Interface Adapters (VIA) this chip has 2 8bit ports for general purpose input/output. 65c22 also enables the computer to have timer
driven interrupts based on its own clock running at 1.8432 MHz. The computer has a SST39SF040 a 512k x 8bit flash rom; only 32k of it is being
used. This hold all the code for the computer's BIOS, memory monitor, mini assembler/disassembler, routines for interfacing with a 128x64 LCD.
In order to communicate with the computer it has a 65c51 Asynchrones Communications Interface Adapter (ACIA); this chip provides serial 
communication over RS232 with the help MAX232 line driver.

### Memory Map

| ---- | ------------- |
| RAM  | $0000 - $4000 |
| ACIA | $5000 - $5004 |
| VIA  | $6000 - $600F |
| ROM  | $8000 - $FFFF |

