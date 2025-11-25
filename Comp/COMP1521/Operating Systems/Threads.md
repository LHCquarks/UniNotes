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
To create process we use:
- `posix_spawn()`
- `fork()` - clone your self
- `exec()`
- `execv()` - kill your self in the process
- `execvp()` - kill your self in the process
To terminate a process we use:
- `exit()`
- `_exit()`
- `kill()`
To monitor a process we use:
- `waitpid()`

## Multi tasking
Multiple process will run on the cpu in turns where we switch between the tasks so quickly that it seems as if they are all running at once.

The time slice that each program is offered is dependent on the machine used.

Typically process that handle user input usually get higher priority

## Concurrency vs parallelism
**Concurrency** is where different process execute by switching back and forth.

**parallelism** is where different process executes at the same time

## Threads
**Threads** share address space reducing the overhead for switching between threads and making it easier to communicate between threads.

Despite them sharing the address space they have different stacks and registers

We can create a new thread with 
```c
int pthread_create(
	pthread_t *restrict thread,
	const pthread_attr_t *restrict attr,
	typeof(void *(void *)) *start_routine,
	void *restrict arg
);
```

### Watch out for thread concurrency issues
- **Race conditions**
- **Deadlocks**
- **Data lifetime**
### Atomic operations
To prevent issues where two threads are reading and writing to a global value at the same time we can use atomic operations.
These operations make sure that read and writes are done in **the same instruction** thus two threads working in parallel will not read and write at the same time. An example is bellow:
```C
#include <pthread.h>
#include <stdatomic.h>

atomic_int global_counter = 0;

void perform_increment(void) {
	global_counter += 1; 
}

void *thread_run(void *data) {
	int n_increments = *(int *)data;
	for (int i = 0; i < n_increments; i++) {
		perform_increment();
	}
	return NULL;
}
```

### Mutex
Another option to prevent threads from reading and writing at the same time is setting a mutex **lock**.

In order to preform an operation on a variable we demand that the thread first acquires the corresponding **lock** ensuring that no other thread is altering the variable during our function. After we are done changing our variable we then give back our lock by calling **unlock**

Corresponding code is bellow:
```C
#include <pthread.h>

int global_counter = 0;
pthread_mutex_t global_lock = PTHREAD_MUTEX_INITIALIZER;

void perform_increment(void) {
	pthread_mutex_lock(&global_lock);
	global_counter += 1;
	pthread_mutex_unlock(&global_lock);
}

void *thread_run(void *data) {
	int n_increments = *(int *)data;
	
	for (int i = 0; i < n_increments; i++) {
		perform_increment();
	}
	
	return NULL;
}
```

A possible problem with this method occurs when multiple locks need to be acquired:

Say there are two locks $A$ and $B$ and two threads $T_1$ and $T_2$.
$T_1$ fetches and gets $A$ whilst $T_2$ fetches and gets $B$. Then say $T_1$ attempts to get $B$ and $T_2$ attempts to get $A$.

Now both threads are waiting for the other thread to finish creating a **deadlock**.

This can easily be avoided by standardizing the order in which locks are fetched and returned
### Data Lifetime
Because we are sharing our data we only get given pointers to our data and so have to fetch it somewhere else. 
The problem occurs if this memory is freed before the thread is finished with it. This can happen when the parent process goes out of scope!

Solutions include **mallocing** relevant data and running `pthread_join(thread_handle)` to make the outer function's lifetime equal to that of the thread