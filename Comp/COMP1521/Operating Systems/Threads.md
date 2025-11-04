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
	- 