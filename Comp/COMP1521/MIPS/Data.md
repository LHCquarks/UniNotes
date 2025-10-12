Data and memory both refers to RAM
## Data types

| Data Type | Size in byes | Location            |
| --------- | ------------ | ------------------- |
| char      | 1            | Memory and Register |
| int       | 4            | Memory and Register |
| pointer   | 4            | Memory and Register |
| array     | Variable     | Memory              |
| struct    | Variable     | Memory              |
## Local vs global variables
### Local
Local variables are stored in registers (if possible)

otherwise it will be stored on the stack
### Global
Global variables are stored in the data segment

## Initializing global data
We can use different directives to initialize different sizes of data

| Directive | Bytes  |
| --------- | ------ |
| .word     | 4      |
| .half     | 2      |
| .byte     | 1      |
| .asciiz   | string |
| .space    | 8      |
All of the above require an initial value to be initializes with except .space

## Loading and storing
First we take an address in a register.
Then we use one of the bellow commands like so
`lb $t0 0($t1)`

| Type    | Load | Store |
| ------- | ---- | ----- |
| 1 byte  | lb   | sb    |
| 2 bytes | lh   | sh    |
| 4 bytes | lw   | sw    |
### Example
```MIPS
main:
	la $t1 my_letter
	lb $t0 0($t1)
	la $t1 my_other_letter
	sb $t0 0($t1)
	
	.data
my_letter:
	.byte 'Y'

my_other_letter:
	.byte 'J'
```
This will load 'Y' into register `$t0`

### What is this cheeky 0?
When we use labels in MIPSY it substitutes values in as offsets not addresses

To fix this we can instead do `my_label + 0`
or as a shortcut we can use `0(my_label)`

## Alignment
When we ask the RAM for an data type at a certain address it will return 4 bytes.

This is because data is stored in chunks of 4 bytes like so:

|        | Byte 1 | Byte 2 | Byte 3 | Byte 4 |
| ------ | ------ | ------ | ------ | ------ |
| 0x0000 |        |        |        |        |
| 0x0004 |        |        |        |        |
| 0x0008 |        |        |        |        |
For this reason it becomes very slow to access *Half words* at 0x0005 or *Words* at 0x0006 ect.

For this reason we align our data to fit nicer into RAM by adding spaces in between data

Eg:
If we have
```MIPS
.data
.half 2
```

|        | Byte 1                             | Byte 2                             | Byte 3 | Byte 4 |
| ------ | ---------------------------------- | ---------------------------------- | ------ | ------ |
| 0x0000 | <span style="color:green">A</span> | <span style="color:green">A</span> |        |        |
| 0x0004 |                                    |                                    |        |        |
| 0x0008 |                                    |                                    |        |        |
And we want to add a word then we need to add 2 bytes of space then add the word with
```MIPS
.space 2
.word 39
```

|        | Byte 1                             | Byte 2                             | Byte 3                            | Byte 4                            |
| ------ | ---------------------------------- | ---------------------------------- | --------------------------------- | --------------------------------- |
| 0x0000 | <span style="color:green">A</span> | <span style="color:green">A</span> | <span style="color:red">_</span>  | <span style="color:red">_</span>  |
| 0x0004 | <span style="color:blue">B</span>  | <span style="color:blue">B</span>  | <span style="color:blue">B</span> | <span style="color:blue">B</span> |
| 0x0008 |                                    |                                    |                                   |                                   |

We can also use the `.align number` directive which reserves space in memory until we have enough space to efficiently access data of size $2^{\text{number}}$ bytes

## Arrays
Items in arrays are stored sequentially in memory

To find the address of an element at index `i` of an array from the address of the start of the array (`addr`) we use `newAddr = addr + i * sizeOf(data)` or in MIPS:
If `i` is in register `$t1`, the size of the data is called `SIZE_OF_DATA` and the address of the array is `Array`:
```MIPS
li    $t2, SIZE_OF_DATA
mul   $t2, $t1   # Find the offset
lw    $t0, Array($t2)
```
### 2d Arrays
To do 2d arrays we make the first index be a large offset equal to the size of each smaller array and the second index as a finer offset for each data entry. 
Eg:

| A   | B   | C   | D   |
| --- | --- | --- | --- |
| E   | F   | G   | H   |
| I   | J   | K   | L   |

is really just

| A   | B   | C   | D   | E   | F   | G   | H   | I   | J   | K   | L   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Hence for `Array[i][j]` we go `Offset = i*ArrayLen*DataLen + j*DataLen = DataLen*(i*ArrayLen + j) = 1*(i*3 + j) = i*3 + j`

## Structs
Structs are just variables with known offsets
eg:
```C
struct student {
	int zid;
	char first[4];
	char last[3];
	int program;
};
```
is

| <span style="color:green">zid</span>      | <span style="color:green">zid</span>      | <span style="color:green">zid</span>      | <span style="color:green">zid</span>      |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| <span style="color:yellow">first</span>   | <span style="color:yellow">first</span>   | <span style="color:yellow">first</span>   | <span style="color:yellow">first</span>   |
| <span style="color:pink">last</span>      | <span style="color:pink">last</span>      | <span style="color:pink">last</span>      | <span style="color:red">_</span>          |
| <span style="color:purple">program</span> | <span style="color:purple">program</span> | <span style="color:purple">program</span> | <span style="color:purple">program</span> |





