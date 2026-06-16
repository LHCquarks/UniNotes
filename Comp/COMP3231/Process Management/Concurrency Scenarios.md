Concurrency scenarios are logical puzzles where a system needs to be devised in order to prevent concurrency issues such as deadlocking and race conditions.
## Producer / Consumer 
### Setup
In the producer consumer problem we have a shared **finite** buffer that **producers** will append items to and **consumers** will remove items from.
![[Pasted image 20260617084540.png]]
For this problem:
- Producers should 
	- Sleep when the buffer is full
	- Wake up when there is empty space in the buffer
- Consumers should
	- Sleep when the buffer is empty
	- Wake up when there are items available
### Naive solution
Without any concurrency control we might make a solution like so:
```C
int count = 0;
#define N 4 /* buffer size */
void producer() {
	while(TRUE) {
		Item it = produce();
		if (count == N)
			sleep(producer);
		insert_item(it);
		count++;
		if (count == 1)
			wakeup(consumer);
	}
}

void consumer() {
	while(TRUE) {
		if (count == 0) 
			sleep(consumer);
		Item it = remove_item();
		count--;
		if (count == N - 1)
			wakeup(producer);
		consume(it);
	}
}
```
This solution in theory covers all our requirements however, there are unprotected critical regions such as when the producers read the global `count` variable and then sleep.
If the producers read the count to be `N` and then the cpu switches to consumer removing the item the producer has already committed to going to sleep and thus will just be put to sleep forever even though there are `N - 1` items in the buffer.

There are many other race conditions in this code that would lead to similar issues.

Anther approach might be to use locks like so
```C
int count = 0;
lock_t buff_lock;
#define N 4 /* buffer size */

void producer() {
	while (TRUE) {
		Item it = produce();
		aquire_lock(buff_lock);
		if (count == N)
			sleep();
		insert_item(it);
		count++;
		if (count == 1)
			wakeup(consumer);
		release_lock(buff_lock);
	}
}

void consumer() {
	while(TRUE) {
		aquire_lock(buff_lock);
		if (count == 0) 
			sleep(consumer);
		Item it = remove_item();
		count--;
		if (count == N - 1)
			wakeup(producer);
		release_lock(buff_lock);
		consume(it);
	}
}
```
The problem with this approach is that we do not release our lock before we go to sleep thus deadlocking all other threads however, if we were to release the lock before we go to sleep then we would be reintroducing the race condition. 

For this to work we would need a way to be able to release a lock and go to sleep atomically. This would be a problem that condition variables could solve however we are going to use another synchronization mechanism more suited to this problem instead.
### Valid solution
Our solution for the producer consumer problem utilizes two semaphores
```C
int count = 0;
lock_t count_lock;
#define N 4 /* buffer size */

// Stores the number of empty slots
semaphore empty = sem_create("empty", N);

// Stores the number of full slots
semaphore full = sem_create("full", 0);

void producer() {
	while (TRUE) {
		Item it = produce();
		P(empty);                  // decrement the number of empty slots
		aquire_lock(buff_lock);
		insert_item(it);
		count++;
		release_lock(buff_lock);
		V(full);                   // increment the number of full slots
	}
}

void consumer() {
	while(TRUE) {
		P(full);                   // decrement the number of full slots
		aquire_lock(buff_lock);
		Item it = remove_item();
		count--;
		release_lock(buff_lock);
		V(empty);                  // increment the number of empty slots
		consume(it);
	}
}
```
### What we can take away from this
Semaphores are really good at dealing with allocating multiple resources of the same type to threads and should be used when dealing with situations involving the distribution of a finite number of resources.
## Dining Philosophers
### Setup
In the dining philosophers problem we have a round table with philosophers trying to eat there spaghetti and one fork for each philosopher as shown in the image below. 
![[Pasted image 20260617092201.png|200]]
Philosophers are weird and require two forks to eat.

In the case where all the philosophers pick up the fork to their left and then their right they will all get deadlocked as their right fork is already taken.

If the philosophers then set down their left fork and then try again they will keep cycling between picking up their left fork and setting it back down (live lock).

In this scenario forks represent locks and philosophers threads. 
### Solutions
#### Global lock
We could also place a global lock on the entire dining table so that only one philosopher at a time may pick up forks. This works but is quite slow due to the entire table getting blocked
#### Global ordering
One solution is to enforce a global ordering of forks and assert that everyone picks up the fork next to them that has the highest number. This way we introduce a bit of asymmetry as for number 0 will not be picked and fork number 4 will be sort after by 2 people. This resolves the deadlock and ensures every philosopher can eat. 
### What we can take away from this
Lock acquisition is important and many deadlock scenarios involving locks can be solved by just enforcing a global ordering on how locks are acquired. Also philosophers are fascinating creatures.
## Readers / Writers
### Setup
Suppose we have some database such as a airline reservation system. We want to be able to have more than one concurrent reader but all writers must have exclusive access (no readers or writers when someone is writing the the database).
### Solution
We can solve this problem with a simple double lock mechanism
```C
lock_t rc_lock = lock_create("read count");
lock_t db_lock = lock_create("data base");
int rc = 0;

void reader() {
	while (TRUE) {
		aquire_lock(rc_lock);
		rc++;
		if (rc == 1) 
			aquire_lock(db_lock);
		release_lock(rc_lock);
		read_data_base();
		aquire_lock(rc_lock);
		rc--;
		if (rc == 0)
			release_lock(db_lock);
		release_lock(rc_lock);
		use_data_read();
	}
}

void writer() {
	while (TRUE) {
		get_write_data();
		aquire_lock(db_lock);
		write_data();
		release_lock(db_lock);
	}
}
```
The problem with this mechanism is that it locks out the writer until all readers are done and the readers can just keep coming in. This is really not fair as the writer can never get the chance to write. 
### What we can take away from this
Due to the very bad draw backs of the solution many professionals recommend that if you have a problem that seems like it needs the reader / writer solution there is most likely a better way to tackle your problem.