### Overview
- A heap is a tree-based data structure which satisfies the <font style="color:lime">heap property</font>.
- The <font style="color:lime">Heap Property</font> details how the heap's data is ordered, and depends on the type of heap:
    - <font style="color:yellow">Max Heap</font> store numbers large to small top down. This means that the value in each node is greater than or equal to the values of its children.
    - <font style="color:yellow">Min Heap</font> store numbers small to large top down. This means that the value in each node is smaller than or equal to the values of its children.
- The <font style="color:lime">Completeness Property</font> is the requirement that all levels of the tree are fully filled, and the lowest level of the tree is filled from left to right.
- A heap effectively works as a [[Priority Queues|priority queue]]
### Binary Heaps
There are many variants of heaps. In this course (COMP2521) we will only consider <font style="color:yellow">Binary Heap</font>. This is a binary tree that follows the heap property (max/min heap) and the completeness property.

```
          13            |         13
         /  \           |        /  \
        /    \          |       /    \
       7      9         |      7      9
      / \    /          |     /      / \
     5   4  2           |    5      2   8
satisfies heap property |satisfies heap property
satisfies completeness  |does not satisfy completeness
 => is a binary heap    | => is not a binary heap
```

The completeness property means that a heap will always have $\lfloor log_2(n)\rfloor + 1$ levels, where n is the number of items in the heap.

### Implementation Details
Heaps are usually implemented using an array, where,
- The `0th` element is not used
- The `nth` level starts at the array's `2nth` index
- Array is in order of the tree's level order traversal. This implies the following useful property:
    - For an item at index `i`:
        - Its left child is located at index `2i`
        - Its right child is located at index `2i + 1`
        - Its parent is located at index `floor(i/2)` 
        (note that integer division in c automatically floors)

This makes it efficient to move up and down the tree, and makes traversal $log(n)$. Note that although resizing is O(n) in the worst-case, this is not counted since the initial size of the heap can be changed according to requirement, and 'worst-case' means worst possible input order, not worst-possible input size.

The binary heap above has the array
```
index:  0   1    2   3   4   5   6   7 
data: |   | 13 | 7 | 9 | 5 | 4 | 2 |   |...
```

- **Insertion**
	1. Add the new item into the last spot into heap
	2. While this item is not the root, and greater than its parent, swap it with its parent (Fix Up or Sift Up)
	3. Add one to the size
	Example:
```c
	void HeapInsert(Heap heap, Item item) {
	// Resizes if the heap is full
		if (heap->numItems == heap->capacity) {
			resizeHeap(heap);
		}
		heap->numItems++;
		heap->items[heap->numItems] = item;
		fixUp(heap->items, heap->numItems);
		return;
	}
	
	static void fixUp(Item items[], int i) {
		while ((i > HEAP_ROOT) && (items[i].value > items[i / 2].value)) {
			// Swap items[i] and items[i/2]
			Item temp = items[i/2];
			items[i/2] = items[i];
			items[i] = temp;
			i = i / 2;
		}
		return;
	}
```
	
- **Deletion**
	1. Switch the root element with the final element in the heap
	2. While the new root is greater than either of its children, swap it with the greater of the two
	3. Decrease the size by one
	4. Return the old root
	The worst-case time complexity of this method is $O(log(n))$
	Example:
```c
	Item HeapDelete(Heap heap) {
		if (heap->numItems == 0) {
			fprintf(stderr, "error: cannot delete from empty heap");
			exit(EXIT_FAILURE);
		}
		Item item = heap->items[HEAP_ROOT];
		heap->items[HEAP_ROOT] = heap->items[heap->numItems];
		heap->numItems--;
		fixDown(heap->items, HEAP_ROOT, heap->numItems);
		return item;
	}
	
	static void fixDown(Item items[], int i, int numItems) {
		while (2 * i <= numItems) {
			// Setting j to the index of i's left child
			int j = 2 * i;
			
			// Sets j to the larger of i's children
			if ((j < numItems) && (items[j].value < items[j + 1].value)) j++;
			// If the larger child is smaller than the parent, we exit
			if (items[i].value >= items[j].value) return;
			
			// Swaps the item
			Item temp = items[i];
			items[i] = items[j];
			items[j] = temp;
			
			// Continue moving down the heap
			i = j;
		}
	return;
	}
```

**Interface**
```c
typedef struct item {
	// Key which items are sorted by
	int value;
	// Add extra fields according to requirement
} Item;

typedef struct heap {
	Item *items;
	int numItems;
	int capacity;
} *Heap;

/**
* Creates and allocates memory for a new empty heap
* Worst-Case Time Complexity: O(1)
*/
Heap HeapNew(void);

/**
* Inserts an item into the heap
* Worst-Case Time Complexity: O(log(n))
*/
void HeapInsert(Heap heap, Item item);

/**
* Deletes the first item in the heap
* Worst-Case Time Complexity: O(log(n))
*/
Item HeapDelete(Heap heap);

/**
* Frees all memory associated with the given heap
* Worst-Case Time Complexity: O(1)
*/
void HeapFree(Heap heap);

/**
* Checks whether the heap is empty
* Worst-Case Time Complexity: O(1)
*/
bool HeapIsEmpty(Heap heap);

/**
* Returns the number of items in the heap
* Worst-Case Time Complexity: O(1)
*/

int HeapSize(Heap heap);
```