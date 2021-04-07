<img src="https://www.calflora.org/app/up/gp/65/13147.jpg" width="100" height="100">

# playful
Feature-complete x86-64 kernel of Phillip's Oppermann's: [Writing an OS in Rust](https://os.phil-opp.com/)

## Overview
The name playful is a play-on-word based off Plagiobothrys nothofulvus, a flower nicknamed Rusty popcorn. Since this *is* a Rust toy kernel, I think the name suits the project quite well. playful is a toy **x86-64** kernel which supports VGA text mode on the QEMU emulator. playful supports a wide range of **interrupts**, including CPU exceptions and double faults, and hardware faults as well thanks to the 8259 PIC (Programmable Interrupt Controller). The kernel also supports **memory management** both via paging and heap allocation. Lastly, **multitasking** operations are currently supported with cooperative multitasking via async/await. Support for preemptive multitasking is coming soon.

## Contents

The table lays out directories and their purposes:

| directory            | description                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------- |
| src/                 | Directory with playful's kernel implementation                                                                 |
| src/allocator.rs     | Heap                                                                                                           |
| src/gdt.rs           | Global descriptor table, used to switch between kernel/user space and load TSS                                 |
| src/interrupts.rs    | Interrupt descriptor table with handlers for CPU exceptions and hardware faults                                |
| lox/main.rs          | Playful's main runner                                                                                          |
| src/memory.rs        | Structures and methods to manage memory and page allocation                                                    |
| lox/serial.rs        | QEMU-to-host bridge via serial ports                                                                           |
| lox/vga_buffer.rs    | Driver for VGA text mode                                                                                       |


## Resources
- [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/)
- [Operating System Concepts](https://www.os-book.com/OS10/)
