
# Embedded Software Portfolio

This is brief overview of some embedded hardware/software projects I have developed over the past few years. The purpose of this site
is to showcase my technical skills as both a competent programmer and engineer.

---

## 65c02 Workbench Computer

The main goal of this project is to meet my needs for programming EEPROMs, controlling external peripherals via SPI, I2C, and UART, driving
other miscellaneous logic devices, and controlling servos using PWM.

The CPU is a WDC 65c02 running at 1 MHz. It includes an AS6C62256 32k x 8-bit static RAM, though the system uses only 16k for the main RAM. 
There is one 65c22 Versatile Interface Adapters (VIA), which features two 8-bit ports for general-purpose input/output. The 65c22 also enables 
the system to have timer-driven interrupts, based on its own clock running at 1.8432 MHz. The computer has a 512k x 8-bit SST39SF040 flash ROM,
with only 32k in use. This holds all the code for the BIOS, memory monitor, mini assembler/disassembler, and routines for interfacing with a 
128x64 LCD. For communication, the system uses a 65c51 Asynchronous Communications Interface Adapter (ACIA); providing serial 
communication over RS232 with the help MAX232 line driver.

### Memory Map

| RAM | $0000 - $4000 |
| ACIA | $5000 - $5004 |
| VIA | $6000 - $600F |
| ROM | $8000 - $FFFF |

---

## JakesteringPi

This is a C library I wrote to control the I/O pins of a Raspberry Pi Zero through its BCM2835 system-on-chip (SoC), enabling direct register access.
I created this library because I found using MicroPython unsatisfactory, and wanted  full control over the hardware. While searching for alternative,
I discovered the WiringPi library by Gordon Henderson, but it had been deprecated by the time I found it. So, I took the initiative to create my own
alternative. I spent the following month (November of 2023) writing the library from scratch.

My main goal was to make the library as simple as possible, with functionality similar to Arduino code. 
For example, `DigitalWrite( pin, value )` and `DigitalRead( pin )` returns value of pin.

