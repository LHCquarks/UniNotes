To prevent race conditions we need to be able to synchronize multiple threads to protect critical regions of our code. This need to protect our data and synchronize is what our synchronization mechanisms are for.
## Locks
This is the most basic type of synchronization mechanism. A lock is such that when one thread has it no other thread can access the critical region of code until the lock holding thread releases the lock.

A typical api for locks is
```C
struct lock;
struct lock *lock_create(const char *name);
void lock_destroy(struct lock *l);
void lock_aquire(struct lock *l);
void lock_release(struct lock *l);
```
To then employ a lock you simply define your lock in global memory, initialize it and then wrap your critical regions acquire and release lock statements.
```C
struct lock *l;
l = lock_create("lock");


void thread() {
	// Do stuff
	
	lock_aquire(l);
	// Critical region
	lock_release(l);
}
```

When `lock_acquire` is run the the thread will atomically check to see if the lock has already been acquired and if not it will set it as acquired. If the lock was already acquired the thread will either sleep or continue checking to see if the lock is free depending on the implementation.

An implementation where the thread will continuously check for the lock to be free is called a **spin lock**.

Often the ability to atomically check and set the lock is provided by the hardware as a check and set instruction that guarantees that interrupts will not occur in between the instructions. 
## Semaphores
Semaphores are like locks but allow a set number of thread.
Developed by Dijkstra, semaphores have an initial number of threads that are allowed and functions `P()` and `V()` are used to increase and decrease this amount respectively.

A typical interface for this object is
```C
struct semaphore;
struct semaphore *sem_create(const char *name, int initial_count);
void sem_destroy(struct semaphore *sem);
void P(struct semaphore *sem);
void V(struct semaphore *sem);
```
`P()` will attempt to reduce the counter of the semaphore by 1. In the case where the counter was zero, `P()` will append the thread to a queue waiting for the counter to be increased and then the thread will be put to sleep.

`V()` will increase the counter by 1 and if it was 0 initially, it will wake up the first thread in the queue.

An example use of this is
```C
int count;
struct semaphore *count_mutex;
main() { 
	count = 0;
	count_mutex = sem_create(“count”, 1);
	if (count_mutex == NULL) 
		panic(“I’m dead”); 
	stuff(); 
}

procedure inc() {
	P(count_mutex); 
	count = count + 1; 
	V(count_mutex); 
} 

procedure dec() { 
	P(count_mutex); 
	count = count –1; 
	V(count_mutex); 
}
```
## Monitors
Monitors are a high level programming language solution to synchronization. Monitors are designed as a single instance that handles requests to shared data so if a thread wants to access some critical region of code / data it has to request for the monitor to do it and the monitor will process the requests in order.
## Conditional Variables
Condition variables are a solution to spin locks so that we do not get blocking taking up resources.
We define a **condition variable** `X` that we can wait on updating `X.wait()` putting us to sleep until another thread updates `X` and called `X.signal()` waking up the first waiting thread.

Another thread can also call `X.broadcast()` to wake up all threads.

An example interface for Conditional variables is
```C
struct cv *cv_create(const char *name); 
void cv_destroy(struct cv *); 

/*
	- Releases the lock and blocks current thread
	- Upon resumption, it re-acquires the lock
		- Note: we must recheck the condition we slept on
*/
void cv_wait(struct cv *cv, struct lock *lock); 

/*
	- Wakes one, does not release the lock 
	- First “waiter” scheduled after signaller releases the lock will reacquire the lock
*/
void cv_signal(struct cv *cv, struct lock *lock); 

/*
	- Wakes all, does not release the lock 
	- First “waiter” scheduled after signaller releases the lock will reacquire the lock
*/
void cv_broadcast(struct cv *cv, struct lock *lock);
```

an example use of conditional variables is 
```C
lock_acquire(c_lock);
while (count == 0) 
	cv_wait(c_cv, c_lock); 
remove_item(); 
count--; 
lock_release(c_lock);
```