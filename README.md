# Universal Machine
Alexander Ravan and Naomi Zarrilli
November 12, 2014

##### An emulator for a simple computer (universal machine) at the machine architecture/ISA level. With 14 instructions, this universal machine is Turing-complete.



### Architecture
The UM runs by first reading in instructions. These instructions are stored in the segment interface, which is a sequence of uarrays. Once all instructions from a .um file are read in, the insturctions are executed. Instructions are loaded from the segmented memory to regsiters, which are used to execute the instructions. The registers are represented as a UArray.

### Registers
The registers abstract direct access to what is held in the registers from other modules. It hides what is held in the register by forcing the client to use getter and setter functions.

### Segment   
This module abstracts how the segmented memory is mangaged from higher level modules. Wrapper functions for all Sequence and UArray function hide what is held in the Segmented memory.  The stack, which hold unmapped segments, is not accessible to any other modules. Therfore umapped segments and the reuse of segment ids is kept a secret from the other modules. Getter and setter functions for segments, the program counter, instructions saved in memory, and  segment length are utilized to abstract the most information from the client and other modules.

### Instruction
This module abstracts all the memory managment, register useage,and direct access to the Memory structure. 

### UM
Abstracts all memory management and instruction execution from the user

This UM would take approximately 2.229 user seconds to execute 50 million instructions. This is calculated after timing midmark.um, which has approximately 85 million instruction and takes 3.79 user seconds to execute.
