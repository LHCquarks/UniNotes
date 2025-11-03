Maps are data types that *map* arbitrary **keys** to arbitrary **data**.

## Implementation
To implement a map we usually use a hash table ADT where:

We have an array which stores our data where the **index** of the array is the value we get from putting the key into a **hash function**

To avoid collisions (two keys map to the same value) we can use the following methods:
### Separate Chaining
Here we let every item in an array to be a linked list to more items. When we then look up the item with the key we hash the key then iterate through the linked list until we find the item.
#### Structs
```C
struct HashTable {
	struct node **slots;
	int tableSize;
	int numItems;
}

struct node {
	Key key;
	Item value;
	struct node *next;
}
```
#### Time complexity
For a hash table with size of $N$ and number of elements is $M$:
- Lookup / Insertion / Deletion
	- Best case: $O(M/N)$
	- Worst case: $O(M)$
	
## Hash functions
Hash functions map keys into ints. 
We want our hash functions to be:
- as one-to-one as possible
- fairly random results
## Key methods
### New
### Free
### Insertion
### Deletion
### Lookup
### Size
