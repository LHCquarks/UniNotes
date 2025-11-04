## Processes
Process are units of computation that have access to various arguments.
Processes are all instances of an executing program with their own **execution sate**.

They all have:
- a process id (PID)
	- PID 1 is called init and is the first processes used to boot the system
	- PIDs are recycled once the int limit is reached
	- can use **getpid()** to get the current PID or **getppid()** to get the parent PID
- children and parent process
	- when a parent process terminates all the children process are inherited by the init process
-  environment variables
	- these are settings related to the environment that a process can read / modify
	- *TZ* - time zone
	- *LANG* - preferred language
	- *HOME* - the home dir
	- *PATH* - where to search for executable
	- passed in via:
		- `extern char **environ;`
		- `int main(int argc, char *argv[], char *env[])`
		- `getenv(char *s)` from `stdlib.h`
	- can be edited through `setenv(const char *envName, const char *value, int overwrite)`
-  designated address space
## Multi tasking
Multiple process will run on the cpu in turns where we switch between the tasks so quickly that it seems as if they are all running at once.

The time slice that each program is offered is dependent on the machine used.

Typically process that handle user input usually get higher priority