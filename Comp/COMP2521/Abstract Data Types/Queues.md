## Overview
A queue is a collection of items such that the first item to enter it the first to leave (FIFO - First in First out). Some examples of this are:
- Waiting lists
- Call centers
- Access to shared resources
- Processes in a computer

Queues support the following operations:
- Enqueue: Add an item to the end of the queue
- Dequeue: Remove the item at the front of the queue
- Size: Return the number of items in the queue
- Peek: Get the front-most item of the queue, without removing it 
## How to implement a queue?
It is easier to use a linked list than an array.
## Interface
```c
typedef struct queue *Queue;

/** Create a new, empty Queue */
Queue QueueNew(void);

/** Free memory allocated to a Queue */
void QueueFree(Queue q);

/** Add an item to the end of a Queue */
void QueueEnqueue(Queue q, Item it);

/** Remove an item from the front of a Queue
Assumes that the Queue is not empty */
Item QueueDequeue(Queue q);

/** Get the number of items in a Queue */
int QueueSize(Queue q);

/** Get the item at the front of a Queue
Assumes that the Queue is not empty */
Item QueuePeek(Queue q);
```

## Time complexity
Using a linked list, use a wrapper struct to contain the tail struct so it can be manipulated easily. Worst-Case Time complexity is O(1) for Insertion, Deletion, Allocating, and Getting Size, and O(n) for freeing and printing

Using an array, keep track of the index of the 'front' of the queue, and when you dequeue the queue, you just move the front index along by one, and treat the data stored before the front index as junk. If you run out of allocated space in the array, looping around back to the junk data slots is allowed. Time complexity is O(1)
