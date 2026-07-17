# CHEP
This is a custom OS for learning how the computer works from loading binaries to a full working OS.

### Tools
* [NASM](https://www.nasm.us/) for assemlbly compilaton.
* [VMWARE](https://www.vmware.com/) for testing the OS.
* [QEMU](https://www.qemu.org/) for running OS images.

### Languages
* [Assembly](https://en.wikipedia.org/wiki/Assembly_language)  is any low-level programming language with a very strong correspondence between the instructions in the language and the architecture's machine code instructions 

### architecture
[x86](https://en.wikipedia.org/wiki/X86-64) is a 64-bit extension of the x86 instruction set.

#### Registers
Types 
- 8-bit registers
- 16-bit registers
- 32-bit registers
- 64-bit registers
- 8-bit registers
- 80-bit registers
- 128-bit registers
- 256-bit registers
- 512-bit registers
##### General purpose registers
Used for keeping indices and pointers.
Here are some of them and there purpose
- RAX (Accumulator): Used in arithmetic and I/O operations. 
- RBX (Base): Used as a pointer to data. 
- RCX (Counter): Used in shift/rotate instructions and loops. 
- RDX (Data): Used in arithmetic and I/O operations. 
- RSI (Source Index): Pointer to source in stream operations. 
- RDI (Destination Index): Pointer to destination in stream operations. 
- RBP (Base Pointer): Points to the base of the stack. 
- RSP (Stack Pointer): Points to the top of the stack. 

##### Status registers
- Zero Flag (ZF): Set if the result of an operation is zero. 
- Carry Flag (CF): Indicates a carry-out from the most significant bit during addition or a borrow during subtraction. 
- Overflow Flag (OF): Signals an overflow in signed arithmetic operations. 
- Sign Flag (SF): Reflects the sign (positive or negative) of the result. 
- Parity Flag (PF): Set if the result has an even number of 1-bits.
- Direction Flag (DF): Controls the direction of string operations (increment or decrement). 
- Interrupt Enable Flag (IF): Determines whether external interrupts are enabled.

##### Segment registers
In x86-64 (long mode), segment registers are largely legacy components used primarily for compatibility, privilege checks, and specific system-level functions.  The architecture treats segmentation as generally disabled for a flat memory model, meaning the base addresses for most segment registers are ignored. 

Segment Register Behavior in 64-bit Mode:

* CS, DS, ES, SS: The base addresses for these segments are always treated as zero, and limit checks are disabled.  This creates a flat memory model where the linear address equals the effective address. These registers are primarily used to determine privilege levels and code execution modes (16-bit, 32-bit, or 64-bit). 
* FS and GS: These are the only exceptions with significant functionality in 64-bit mode.  Their base addresses are not ignored and can be set to non-zero values via Model-Specific Registers (MSRs) or dedicated instructions like WRFSBASE and WRGSBASE.  This allows them to serve as base registers for thread-local storage (TLS) and CPU-specific data access. 
* Legacy Support: Segment registers remain essential for running legacy 16-bit and 32-bit applications in compatibility modes and for transitioning between real mode and protected/long mode during boot or context switches. 

### Referencing a memory location
segment = [base + index * scale + displacement]

#### [The stack](https://en.wikipedia.org/wiki/Stack-based_memory_allocation)
- Memory accessed in a FIFO( First In First Out) manner using push ansd pop.