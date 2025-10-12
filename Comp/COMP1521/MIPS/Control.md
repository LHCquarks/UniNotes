Control is just conditional programming (If statements) and looping.

## Branching instructions

| Instruction | Comparison               |
| ----------- | ------------------------ |
| B           | None                     |
| BEQ         | $R_1 = R_2$              |
| BEQZ        | $R_1 = 0$                |
| BNE         | $R_1 \not= R_2$          |
| BNEZ        | $R_1 \not = 0$           |
| BGE         | $R_1 \ge R_2$            |
| BGEU        | $R_1 \ge R_2$ (Unsigned) |
| BGEZ        | $R_1 \ge 0$              |
| BGT         | $R_1 > R_2$              |
| BGTU        | $R_1 > R_2$ (Unsigned)   |
| BGTZ        | $R_1 > 0$                |
| BLT         | $R_1 < R_2$              |
| BLTU        | $R_1 < R_2$ (Unsigned)   |
| BLTZ        | $R_1 < 0$                |
| BLE         | $R_1 \le R_2$            |
| BLEU        | $R_1 \le R_2$ (Unsigned) |
| BLEZ        | $R_1 \le 0$              |
|             |                          |

## How to use
To branch to another code path we can use labels and branching instructions. To jump to code with the label `doSomething` we write
```MIPS
main:
	li  $t0 4
	li  $t1 4
	BEQ $t0 $t1 doSomething

doSometing:
	# Do Something
```

## Shortcuts
When writing our functions MIPS will just continue incrementing down the program if it is not told to jump somewhere. 
This means sometimes we can just ignore some of the branch statement 
Eg:
Instead of writing
```MIPS
main:
	# Code here
	BQE $t0 $t1 doSomething
	B continueProgram

doSomething:
	# Do something
	B continueProgram

continueProgram:
	# Rest of program
```

```MIPS
main:
	# Code here
	BLT $t0 $t1 continueProgram

doSomething:
	# Do something

continueProgram:
	# Rest of program
```

## Branching vs Jumping
Branching takes the current position of the code and "jumps" forward by the given offset.
`PC += Offset`

In contrast jumping goes directly to an address.
`PC = Addr`

Note:
	On top of this, jump uses 26 bit addresses whereas branch uses 16. This means that we could jump way further with jump