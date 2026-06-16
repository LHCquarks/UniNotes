To prevent race conditions we need to be able to synchronize multiple threads to protect critical regions of our code. This need to protect our data and synchronize is what our synchronization mechanisms are for.
## Locks
This is the most basic type of synchronization mechanism. A lock is such that when one thread has it no other thread can access the critical region of code until the lock holding thread releases the lock.

A typical api for locks is
```C
struct lock;

void lock_initialize(*struct lock l);
void lock_aquire(*struct lock l);
void lock_release(*struct lock l);
```
To then employ a lock you simply define your lock in global memory, initialize it and then wrap your critical regions acquire and release lock statements.
```C
struct lock l;
lock_initialize(&l);


void thread() {
	// Do stuff
	
	lock_aquire(&l);
	// Critical region
	lock_release(&l);
}
```

When `lock_acquire` is run the the thread will atomically check to see if the lock has already been acquired and if not it will set it as acquired. If the lock was already acquired the thread will either sleep or continue checking to see if the lock is free depending on the implementation.

An implementation where the thread will continuously check for the lock to be free is called a **spin lock**.

Often the ability to atomically check and set the lock is provided by the hardware as a check and set instruction that guarantees that interrupts will not occur in between the instructions. 
## Semaphores

## Monitors

## Conditional Variables