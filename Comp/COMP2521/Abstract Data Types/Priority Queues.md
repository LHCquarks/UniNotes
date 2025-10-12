### Overview
- A Priority Queue is an abstract data type (or a data structure) which are 
similar to queues, but each item has an associated priority, and the dequeued 
item is always the one with the highest priority, regardless of Enqueue order.
**Examples and Applications**
- Hospital Waiting Rooms
- Incident Management
- Huffman Coding
- Dijkstra's Algorithm
- Prim's Algorithm

A priority queue supports the following main operations:
- `Insert` - Insert an item with an associated priority.
- `Delete` - Delete (and return) the item with the highest priority.
- `Peek` - Get the item with the highest priority without deleting it.
- `IsEmpty`- Check if the priority queue is empty.

Depending on the implementation, either large or small priority may be taken to mean 'high priority'

### Worst-Case Time Complexities using different implementations
- Unordered Array:
    - Insertion: O(1)
    - Deletion: O(n)
    - Peek: O(n)
    - IsEmpty: O(1)
- Ordered Array:
    - Insertion: O(n)
    - Deletion: O(1)
    - Peek: O(1)
    - IsEmpty: O(1)
- Unordered Linked List:
    - Insertion: O(1)
    - Deletion: O(n)
    - Peek: O(n)
    - IsEmpty: O(1)
- Ordered Linked List:
    - Insertion: O(n)
    - Deletion: O(1)
    - Peek: O(1)
    - IsEmpty: O(1)

We can use a [[Heaps|heap]] data structure to escape this O(n) time complexity. This results in a worst-case time complexity of O(log(n)) for insertion and deletion, and Peek and IsEmpty remain at O(1).