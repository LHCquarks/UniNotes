## Compilers
### Clang
`clang` is the compiler that will be used in this course. It works the same as `gcc` with the main compile command looking like:

`clang -Wall -Werror -g -fsanitize=SANITIZER -o executeablename filename.c`

where `SANITIZER` represents the [[#Sanitizers]] you want to use (`address` or `memory`).

Some common error messages are detailed in [[Error Messages.canvas|Error Messages]]

#### Options
##### -Wall
Catches a bunch of warnings
##### -Werror
Turns warnings into errors so it will not compile
##### -g
Include debuging information such as line numbers and function names
##### -fsanitize
Catches use after free, memory leaks ect
###### Sanitizers
1. Address - detects invalid memory access
2. Leak - makes sure not to leak memory
3. Memory - Checks if a variable has been initialized
4. Undefined - Checks for undefined behaviour such as integer overflows

Valgrind - Valgrind is a program that tracks many memory related bugs and is run with
```Bash
valgrind ./program
```

### Make

Make is a program that compiles program using a Makefile.
Make uses another compiler specified in the Makefile to compile a program.

```Bash
make
```
will compile the code whilst 
```Bash
make clean
```
will delete binaries made in a previous make compilation

Make is preferred for large projects because of the simple command