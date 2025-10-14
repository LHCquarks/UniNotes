Linux *syscalls* for manipulating files

| id  | Name  | Function |
| --- | ----- | -------- |
| 0   | read  |          |
| 1   | write |          |
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
## C wrappers
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
| O_TRUNC  |                                |
`mode_t mode` describes the permissions to set for the newly created file

When we open a file we need to **close** a file just like freeing memory

### Close
To close a file we use `int close(int fd);`.

### Read
To read from a file we use
`ssize_t read(int fd,);` 


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
and returns the number of bytes were actually writen
### Dup2
`Dup2` duplicates the contents a file into another file.
The signature is:
`int Dup2(int oldfd, int newfd);`




