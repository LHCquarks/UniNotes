Linux *syscalls* for manipulating files

| id  | Name  | Function |
| --- | ----- | -------- |
| 0   | read  |          |
| 1   | write |          |
| 2   | open  |          |
| 3   | close |          |
| 4   | stat  |          |
| 8   | Iseek |          |
| 33  | dup2  |          |
Hello world but different:
```C
#include <unistd.h>
int main(void) {
	char bytes[13] = "Hello World!\n";
	
	syscall(1, 1, bytes, 12); // prints bytes to stdout
	// we can also use the wrapper
	write(1, bytes, 12);
	return 0;
}
```

These syscall wrappers only work on Linux and just give the syscall a name in your program.

## File in memory
In Linux files are just a bunch of bytes. The metadata does not record the file type nor does the extension!

Files typically live on a disc (hard drive or ssd)

Discs are not like ram where you can just read and write to it. This is because we need drivers to interact with them which live in the OS. This means we have to run syscalls to handle it

## File descriptors
When we open a file a unique file descriptor is created in the **file descriptor table**.

Every processes starts with 3 files:

| name   | function                  | index |
| ------ | ------------------------- | ----- |
| stdin  | connected to the keyboard | 0     |
| stdout | connected to the terminal | 1     |
| stderr | connected to the terminal | 2     |
When you open a file a new **file descriptor** will be returned. If you wish to write to a file you need to use this **file descriptor**

The kernel stores a table of these file descriptors to remember what flags a file was opened with and to enforce those flags
## Base C wrappers
### Errors
If the syscall returns an error then all the C wrappers will return -1 and set errno to an integer value which can be decoded with `<stderr.h>`.

All the error codes can be found with `man 3 errno`
### Open
`#include <fcntl.h>`

To open a file we know exists we use the command `int open(char *pathname, int flags);`

If we want to make a new file we use the command `int open(char *pathname, int flags, mode_t mode);`

when successful **open** will return a file descriptor for a new file

| Flag     | Use                            |
| -------- | ------------------------------ |
| O_RDONLY | To read from a file            |
| O_WRONLY | To write to a file             |
| O_RDWR   | To read and write to a file    |
| O_APPEND | To append to the end of a file |
| O_CREAT  | Create a file if none existed  |
| O_TRUNC  | Truncates the file to length 0 |
`mode_t mode` describes the permissions to set for the newly created file

When we open a file we need to **close** a file just like freeing memory

### Close
To close a file we use `int close(int fd);`.

### Read
`#include <unistd.h>`
To read from a file we use either:
`ssize_t read(int fd, void* buf, size_t n_byte);` 
`ssize_t read(int fd, void* buf, size_t n_byte, off_t offset);` 

| argument | description                                                  |
| -------- | ------------------------------------------------------------ |
| fd       | the file descriptor to read from                             |
| buf      | the buffer to read the file's content into                   |
| n_byte   | the number of bytes that are able to be stored in the buffer |
| offset   | an offset into to file to start reading from                 |
Returns the number of bytes read
### Write
`#include <unistd.h>`
To write to a file we use
`ssize_t write(int fd, const void *buf, size_t count);`
where:

| argument | description                     |
| -------- | ------------------------------- |
| fd       | the file descriptor to write to |
| buf      | the buffer to write from        |
| count    | how many bytes to write         |
Returns the number of bytes actually written (memory might be full)
### Dup2
`Dup2` duplicates the contents a file into another file.
The signature is:
`int Dup2(int oldfd, int newfd);`





## stdio functions
Unlike the base C wrappers the stdio functions will work on all OS's and so is recommended to use this.
### FILE struct
The FILE struct is used through the std libc library.
The FILE struct is called an opaque struct meaning changes depending on the OS
### General structure
- `f` at the *end* means that it has a format string. Think `printf`
- `f` at the *front* means that you can specify the FILE to write to
### Functions

| function | signature                                                                                              |
| -------- | ------------------------------------------------------------------------------------------------------ |
| printf   | `int printf(const char *restrict format, ...);`                                                        |
| scanf    | `int scanf(const char *restrict format, ...);`                                                         |
| snprintf | `int snprintf(size_t size, char str[restricted size], size_t size, const char *restrict format, ...);` |
| sscanf   | `int sscanf(const char *restrict str, const char *restrict format, ...);`                              |
| puts     | `int puts(const char *s);`                                                                             |
| gets     | `char *gets(char *s);` NOTE: Deprecated for security reasons                                           |
| putchar  | `int putchar(int c);`                                                                                  |
| getchar  | `int getchar(void);`                                                                                   |
| fopen    | `FILE *fopen(const char *pathname, const char *mode);`                                                 |
| fclose   | `int fclose(FILE *stream);`                                                                            |
| fgetc    | `int fgetc(FILE *stream);`<br>                                                                         |
| fputc    | `int fputc(int c, FILE *stream);`                                                                      |
| fread    | `size_t fread(void *ptr, size_t size, size_t nmemb, FILE *stream);`                                    |
| fwrite   | `size_t fwrite(const void *ptr, size_t size, size_t nmemb, FILE *stream);`                             |
| fgets    | `char *fgets(char *s, int size, FILE *stream);`                                                        |
| fputs    | `char *fputs(char *s, FILE *stream);`                                                                  |
| fscanf   | `int fscanf(FILE *restrict stream, const char *restrict format, ...);`                                 |
| fprintf  | `int fprintf(FILE *stream, const char *format, ...);`                                                  |
| fseek    | `int fseek(FILE *stream, long offset, int whence);`                                                    |
| ftell    | `long ftell(FILE *stream);`                                                                            |
| fflush   | `int fflush(FILE *_Nullable stream);`                                                                  |
### Buffering
To reduce the amount to system calls when printing / scanning data we store all our io into a buffer. After a while this buffer will get 'flushed' which will actually make a syscall to write / read the data.

Print functions are flushed automatically when a new line charter is printed

## Seeking
To change our position within a file we can use **seek** functions which allow us to go to:
- the start / end of a file
- a certain position in the file
- an offset from your current position

To find where we are in a file we can use **tell**
### Size of a file
To find the size of a file first jump to the end of a file then use tell