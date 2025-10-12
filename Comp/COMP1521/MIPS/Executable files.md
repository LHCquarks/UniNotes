
The computer is unable to run text files like .c files so we have to first convert this to a executable file.

An executable file is a set of byte values stored on a hard drive / ssd. It starts with the ".ELF"  header and then has the program data.

When we execute the program we first load it into RAM and then tell the CPU what line to start executing it on.

.ELF files contain a:
- text / code section where the instructions are stored
- Data segment which store global variables for the program

Out of the .ELF file is the:
- Heap that dynamically grows and shrinks with malloc
- Stack with local variables made by the compiler

All these are put together in the RAM
