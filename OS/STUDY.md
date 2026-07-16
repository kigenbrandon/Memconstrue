# HOW A COMPUTER STARTS UP
* BIOS is copied from a [ROM]() chip to [RAM]().
* BIOS starts executing code.
    - Initializes hardware.
    - runs some tests [POST]() (Power On Self Test)
* BIOS starts to search for an [OS]() to start.
* BIOS loads and starts the OS.
* OS runs.

# HOW THE BIOS FINDS AN OS
This are the methods of how the BIOS finds the OS and starts executing.
## Legacy booting
* BIOS loads the first sector of each bootable device into memory (at location 0x7c00).
* BIOS checks for 0xAA55 signature.
* If found it starts executing code.
## EFI
* BIOS looks into special EFI partitions.
* OS must be compiled as an EFI program.