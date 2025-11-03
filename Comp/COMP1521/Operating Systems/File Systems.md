A file system has multiple components:
- Files: a named collection of bytes
- Directories
- Metadata

## File Names
File names can take any byte except for \0 and /. Max file name is usually 255 chars.

. and .. are files in every directory and refer the the current and parent directory respectively

.___ refers to a hidden file which will generally not be displayed by default

## Metadata
Every file has a inode associated with it which can be used to look up the metadata of a file in a inode table.

Metadata stores:
- Location
- age
- last modified
- permissions ect
## Inode
Every file string is mapped to an inode which is mapped to metadata and the file continence 

## Permissions
Every file has:
- Read `r`
- Write `w`
- Execute `x`
permissions for each of the following users:
- owner
- group
- other
### Example
```
  O  G  O   Size Owner   Date       File name
drwxr-xr-x     - kais 25 Jan  2023   mazes
.rw-r--r--   331 kais 25 Jan  2023   analysis.txt
.rw-r--r--   155 kais  6 Jul  2023   cell.h
.rw-r--r--  1.1k kais  3 Aug  2024   Makefile
.rw-r--r--  1.9k kais 19 Oct  2023   matrix.c
.rw-r--r--  1.5k kais 12 Mar  2024   matrix.h
.rw-r--r--  9.0k kais 12 Mar  2024   Maze.c
.rw-r--r--  3.1k kais 12 Mar  2024   Maze.h
.rw-r--r--  1.2k kais  7 Sep  2024   Queue.c
.rw-r--r--  1.2k kais 12 Mar  2024   Queue.h
.rw-r--r--   171 kais 25 Jan  2023   solve.h
.rwxr-xr-x  2.3M kais 29 Oct 08:35  󰡯 solveBfs
.rw-r--r--  2.2k kais 29 Oct 08:35   solveBfs.c
.rwxr-xr-x  2.3M kais 29 Oct 09:24  󰡯 solveDfs
.rw-r--r--  2.2k kais 29 Oct 09:24   solveDfs.c
.rwxr-xr-x  2.3M kais 29 Oct 07:57  󰡯 solveDfsBacktrack
.rw-r--r--   311 kais 20 Oct  2023   solveDfsBacktrack.c
.rwxr-xr-x  2.3M kais 29 Oct 07:57  󰡯 solveFollowWall
.rw-r--r--   306 kais  1 Jul  2024   solveFollowWall.c
.rw-r--r--  1.7k kais 25 Jan  2023   solver.c
.rw-r--r--  1.1k kais  7 Sep  2024   Stack.c
.rw-r--r--  1.2k kais 12 Mar  2024   Stack.h
```
### Execute directory???
Executing a directory just allows the user to explore it
### Chmod command
The Chmod command is how you change the permissions of a file / directory and can be used in the following ways: 
#### Symbolic
We first specify which user's assess will be changed where:
- `u` is the user who owns the file
- `g` is the group who has access to the file
- `o` is everyone else
- `a` set for all users
We then set the permissions they have eg:
`chmod urwx file_name.txt` will change the owner's permissions to read write and execute
#### Octal
For each group we represent their permissions with a single octal digit.
Eg: ``



## Links
### Hard Links
Hard links make multiple file paths link to the same inode. This means they will not work between different machines because they link to different inodes
### Symlinks
Symlinks point one path name to another path name
## Shell expansions
