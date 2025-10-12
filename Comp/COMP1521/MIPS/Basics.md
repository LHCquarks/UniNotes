## Background
### What is assembly?
[[Executable files |Machine code]] is hard to write, so instead we write our instructions in assembly. 

In assembly, instructions are mapped one to one to machine code instructions.

We might write
```
addi $t1, $t0, 12
```
which might map to 
```
001000 01000 01001 0000000000001100
```

### Compiling from C to assembly
gcc first will compile to assembly and then to machine code.
You can see this with the command
```Bash
$ gcc -S helloWorld.c
```

### Why write in assembly
#### Finding security vulnerabilities
Sometimes security vulnerabilities are not obvious until you are able to look at the exact commands the CPU is running. For this reason, often C is compiled to assembly to analyse vulnerabilities
#### Optimise for performance
This is mostly only for small parts of code that gets run over and over again but being able
to control the exact behaviour of a program can lead to large time saves
#### Writing Drivers
Often we have to write to specific registers and do so with very specific commands. This is often done in assembly so we can communicate with devices via functions in higher level languages

### CPU architectures
Different CPUs use different architectures and so the binary is going to be different
Examples are:
- x86
- ARM
- RISC-V
- MIPS
## What is MIPS
MIPS is a computer architecture that was used in the Nintendo64 and old supercomputers
## MIPS Architecture
In a MIPS CPU we have:
- Data registers
- Control registers
- Control unit (CU)
- Arithmetic logic unit (ALU)
- Floating-point unit (FPU)
- Caches 
- Connection to Memory / RAM
### Registers
Registers are specialised components that store data. They are apart of the CPU and so have a
massive speed boost compared to memory.

All data must be loaded to a register before the CPU can perform any operations with it

#### Types of registers
There are:
- 32 general purpose registers on the CPU
- Some Floating point registers
-  Hi/Lo registers for multiplication and division
- One program counter (to keep track of where in the program we are)
- A few other special registers
#### How to reference each register
Registers are denoted by a $ sign then the type of the register and finally what number register is being called.
The types are as follows:

| Register/s | Description                                                                                                              |
| ---------- | ------------------------------------------------------------------------------------------------------------------------ |
| $zero      | The **zero** register that always has a zero in it. All writes are discarded                                             |
| $at        | The **a**ssembler **t**emporary register. Reserved for assembler use                                                     |
| $v0 - $v1  | The **v**alue from an expression evaluation or function return                                                           |
| $a0 - $a3  | First four **a**rguments to a function / subroutine                                                                      |
| $t0 - $t9  | **T**emporary. Must save these when calling another subroutine as they may be overwriten                                 |
| $s0- $s7   | **S**aved. Will be saved between subroutines                                                                             |
| $k0- $k1   | **K**ernal use                                                                                                           |
| $gp        | **G**obal **P**ointer (the address of global area)                                                                       |
| $sp        | **S**tack **P**ointer (top of the stack)                                                                                 |
| $fp        | **F**rame **P**ointer (the bottom of the current stack frame) - If not using a frame pointer will become a save register |
| $ra        | **R**eturn **A**ddress of the most recent caller                                                                         |
### Memory
MIPSY's memory is partitioned as follows:
![[Pasted image 20250915133242.png]]

| Segment | Base       | Description                                                                                                                                                                                                                                                                                                                                      |
| ------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Text    | 0x00400000 | Where user program code resides; <br>In mipsy, it is the only area of memory where instructions are executable;<br>its initial size is 256 kiB. <br>This is the only area of memory where instructions are executable. In mipsy, this area of memory is also writeable.  <br>On a real system, this area of memory would generally be read-only. |
| Data    | 0x10000000 | Where user data resides; <br>its initial size is 256 kiB, but its size is not fixed, and can be changed with the *sbrk* syscall up to a maximum of 1 MiB.                                                                                                                                                                                        |
| Stack   | 0x7ffffeff | The function call stack; <br>grows towards negative addresses. <br>Its initial size is 64 kiB, but it will grow as needed up to a maximum of 256 kiB.                                                                                                                                                                                            |
| k_text  | 0x80000000 | Kernel executable code                                                                                                                                                                                                                                                                                                                           |
| k_data  | 0x90000000 | Kernel data                                                                                                                                                                                                                                                                                                                                      |
## Loading values to Registers
We use the command li to load a value into a register
```MIPS
li $t0, 2
```
An example program is
```MIPS
li $t0, 2
li $t1, 3
mul $t2, $t1, $t2
```

### Hexadecimal representation
For the most part we represent an address and binary data in hexadecimal as it is easy to see if something aligns with 32 bits ect.
## Style
Refer to the style guide on the course website [here](https://jashankj.space/notes/cse-comp1521-better-assembly/)

## Returning
```MIPS
main:
	#Your Code
	
	li $v0, 0
	jr $ra
```
Here `li $v0, 0` loads the return value of 0 into the variable register then `jr $ra` sends the code execution back to the previous process

## Syscalls
Syscalls call other functions from the OS to do work for us.
To make a syscall we put the syscall number into `$v0` and then run syscall.
Basic syscalls are below

| Service      | $v0 | Arguments                             | Returns     |
| ------------ | --- | ------------------------------------- | ----------- |
| printf("%d") | 1   | int in $a0                            |             |
| fputs        | 4   | string addr in $a0                    |             |
| scanf("%d")  | 5   | none                                  | int in $v0  |
| fgets        | 8   | Line to return $a0, max length in $a1 |             |
| exit(0)      | 10  | none                                  |             |
| printf("%c") | 11  | char in $a0                           |             |
| scanf("%c")  | 12  | none                                  | char in $v0 |

## Instruction types
Instructions are split into 3 different types which have:
- <span style="color:red">The code (type) of the operation being run</span>
- <span style="color:green">The arguments for the operation</span>
- <span style="color:blue">Constant value</span>
### R-type
![[Pasted image 20250917100643.png]]
### I-type
![[Pasted image 20250917100701.png]]
### J-type
![[Pasted image 20250917100718.png]]
## Labels
Labels represent addresses which we can load data into.
This is done in the `.data` section and the labels are denoted with a name followed by a colon as below
```MIPS
.data
Hello_World:
	.asciiz "Hello World\n"
```

## Common operations