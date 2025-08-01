#The Build Process
The process of converting the high level source code representation into an executable binary image.

Five key steps are involved:
- Pre-processing
- Compiling
- Assembling
- Linking
- Locating

<img width="1001" height="161" alt="TheBuildProcess_figure" src="https://github.com/user-attachments/assets/81af080b-1b8c-4337-b393-1e50bbfdfe22" />







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



