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
### Linear Probing
On insertion we go to the index dictated by the hash function and if it is already used we increase the the index by one.

On lookup we go to the index dictated by the hash function and check if has the key we used. Otherwise we keep increasing the index until we get to the value. If we come across an empty value then we through an error as it was not in the hashmap

Deletion has 2 methods:
- **Back shifting**:
	- Remove the item and push all items on it's right to the left by one to fill in the gap
	- Long deletion but efficient lookup
- **Tombstone**:
	- Replace the item with a **deleted** marker. We then treat this as empty for insertion but filled during lookup
	- Can result in longer lookups but more efficient deletion
#### Structs
```C
struct HashTable {
	struct slot *slots;
	int tableSize;
	int numItems;
}

struct slot {
	Key key;
	Item value;
	bool used;
}
```
#### Time complexity
- Lookup: 
	- successful search: $O(\frac{1}{1 + \alpha})$
	- unsuccessful search: $O(\frac{1}{(1 + \alpha)^2})$
### Double hashing
Similar to linear probing, when we get a collision we add a special number to the index. Only this time this special number is the key hashed a second time.

By hashing the key another time we get more *random* behavior, reducing the chance of our items clustering together.
#### Structs

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
