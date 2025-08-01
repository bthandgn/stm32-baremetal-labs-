# The Build Process
The process of converting the high level source code representation into an executable binary image.

Five key steps are involved:
- Pre-processing
- Compiling
- Assembling
- Linking
- Locating

<img width="1001" height="161" alt="TheBuildProcess_figure" src="https://github.com/user-attachments/assets/81af080b-1b8c-4337-b393-1e50bbfdfe22" />

## Pre-Processing
### Purpose
- Handles directives like "#include" ,"#define" and conditional compilation("#if",'#ifdef', etc.). It prepares the source code for compilation by expanding macros and resolving file inclusions.
### Output
- A translation unit(.i or .ii file) with all preprocessor instructions resolved into plain source code. 

## Compiling
### Purpose
- Translates high-level C/C++ code into assembly instructions specific to the target architecture.
### Output
- An assembly file (.s or .asm) representing the program logic in human-readable machine instructions.

## Assembling
### Purpose
- Converts the assembly code into machine code (object code) by encoding instructions into binary format.

### Output
- An object file (.obj or .o) containing relocatable machine code and metadata like symbol tables.

## Linking
### Purpose
- Resolves symbol references between object files and libraries, merges sections (e.g., .text, .data), and organizes them into a final program structure.

### Output
- An executable image (.elf, .out) with all dependencies resolved.

## Locating
### Purpose
- Maps sections of the executable to specific memory regions based on a linker script, ensuring proper placement for flash, RAM, and peripheral-mapped areas.

### Output
- A final binary (.bin, .hex, etc.) ready for programming onto the target hardware.


<img width="1001" height="161" alt="TheBuildProcess_figure" src="https://github.com/user-attachments/assets/8cb72f2e-d554-4bf8-9742-6505474e03ca" />




# GNU tools

## arm-none-eabi-gcc
- This command compiles, assembles and links the code.
Example:
Arm-none-eabi-gcc (source file) -o (output file) 	           
E.g : arm-none-eabi-gcc main.c -o main.o		              

Arm-none-eabi-gcc (source file) -o (output file)  ------- > o: Compile, Assemble and Link to output file.



|        Option      |                                   Purpose                                          |
|-------------------|------------------------------------------------------------------------------------|
|-c	                 | Compile and Assemble, do not Link                                                  |
|-o [FILE]	         | Compile,Assemble and Link to output File E.g: -o main.o                            |
|-g                  | Generate Debugging Information in Executable                                       |
|-Wall	             | Enable All Warning Messages                                                        |
|-Werror	           | Treat all Warnings as Error                                                        |
|-I[DIR]	           | Include this DIR to look for header files                                          |
|-ansi               | Specify which standard version to use                                              |
|-std = STANDARD	   | Specify which standard version to use                                              |
|-v	                 | Verbose output from GCC                                                            |
|-mcpu = [NAME]      | Specifies the target ARM Processor and architecrute E.g. -mcpu = cortex-m4         |
|-march = [NAME]	   | Specifies the target ARM Architecture E.g: -march = armv7-m                        |
|-mtune = [NAME]	   | Specifies the target ARM Processor E.g: -mtune = cortex-m4                         |
|-mthumb	           | To generate code in Thumb Instruction Set Architecture(ISA)                        |
|-marm	             | To generate code in ARM Instruction Set Architecture(ISA)                          |
|-mlittle-endian	   | To generate code for little endian mode                                            |
|-mbig-endian	       | To generate code for big endian mode                                               |


Example: arm-none-eabi-gcc -c -mcpu=cortex-m4 -mthumb main.c -o main.o

-c: Compile and Assemble, Do not Link

-mcpu=cortex-m4: Processor

-mthumb: Instruction Set

main.c : Source File

main.o : Output File

## arm-none-eabi-nm
- List the symbols from object files

## Arm-none-eabi-size
- List the section sizes of object and executable files

## arm-none-eabi-objdump
- Dumps information about an object file
- Used to analyze an object files

## arm-none-eabi-readelf
- Display information from elf files

## arm-none-eabi-obcopy
- Used to convert object files from one format to another
- Also used to make a copy of an object file



