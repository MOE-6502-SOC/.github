# MOE-6502-SOC
This organization contains all components built for the implementation of
the *Mac's Out Engineering 6502 SoC*.

## Project Goal
The personal goal of this project is to learn about computer architecture and
implementations of processors at the Register Transfer Level. Beyond that, the
goal of this project is to create many generic RTL components that could be
extended for use with different vendor products and tools, and be generic enough
that they can be used in unrelated designs. The hope is that if an individual or
group does not have to put in too much effort to port the design to a platform
which the SoC was not originally developed for.

## Project Inspiration
This project was inspired by
[Ben Eater's 65c02-based computer from scratch](https://eater.net/6502)
kit and video series. The thought is, this project could be used as an additional
learning tool for those who want a different perspective or who want to dive
deeper into "Computer Architecture" concepts.

## SoC Architecture
The SoC implementation contains thefollowing components to give the user a 
functioning 6502 system *(Thus the title system on a chip)*:
<!-- TODO: Add links to these. -->
  - [6502 Implementation]()
  \- Modeled after the [W65C02S](https://eater.net/datasheets/w65c02s.pdf)
  processor. Note, this is not the original [6502](https://en.wikipedia.org/wiki/MOS_Technology_6502).
    - This implementation is not pin-for-pin the same as the W65C02S. For example, due to the lack of
internal tri-states in most modern FPGAs, the memory data bus of the processor as is can not be implemented;
instead, a more FPGA friendly memory bus implementation is used, Wishbone. For further details of differences
between the this component and what is shown in the data-sheet, see the documentation for this component.
  - [Memory Implementation]()
  \- TODO: Not yet, decided.
  - [Versatile Interface Adapter (VIA)]()
  \- Modeled after the [W65C22](https://eater.net/datasheets/w65c22.pdf). This
  is a component that allows a designer to perform "normal" I/O operations with
  peripherals, such as an LCD.

**Note: All implementations of SoC components are purely behavioral and**
**between-cycle timing requirements are not modeled. Per-cycle behavior is**
**modeled, but all timing requirements should be met via Place and Route tooling.**

### SoC Block Diagram
TODO: This still needs made and added.
## Hardware Targets
The SoC Implementation does not contain (**Should not for developers**) any vendor
specific element instantiations, nor is it ready to instantiate on an FPGA . The
repositories named with the format `target_moe_6502_<FPGA vendor name>_<target name>`
shall contain all board/FPGA specific implementation details *(These repositories*
*will instantiate the MOE 6502 SoC)*.

### Original Target
The original target hardware of this design is the
[Digilent Nexys Video Board](https://digilent.com/reference/programmable-logic/nexys-video/start).
At the heart of this board is the ***Xilinx Artix-7 XC7A200T***.
### Additional Targets
The hope is when others implement this SoC for their own target, they add to
this organization.
