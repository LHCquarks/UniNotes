`clang` is a more useful sanitiser than `gcc` because it gives very details error messages (tells you which line the error occurred on, and function calls which led up to that), and can catch some memory leaks and incorrect usage of memory addresses which `gcc` can't. Usage:

`clang -Wall -Werror -g -fsanitize=SANITIZER -o executeablename filename.c`

where `SANITIZER` represents the sanitizer you want to use (`address` or `memory`).


Some common error messsages are detailed in [[Error Messages.canvas|Error Messages]]