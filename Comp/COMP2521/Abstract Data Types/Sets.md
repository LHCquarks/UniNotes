## Overview
A set is an unordered collection of distinct elements.

Basic set operations:
- Create an empty set
- Insert an item into the set
- Delete an item from the set
- Check if an item is in the set
- Get the size of the set
- Display the set

## How to Implement a Set?
- Unordered arrays
	- Lookups are $O(n)$
	- Inserting takes $O(1)$
	- Removing requires an $O(n)$ lookup then override with last element ($O(1)$)  so $O(n)$
- Ordered Arrays
	- Can use binary search so lookups are $O(\log n)$
	- Inserting requires an $O(\log n)$ lookup and a $O(n)$ shift giving $O(n)$
	- Removing requires an $O(\log n)$ lookup and a $O(n)$ shift giving $O(n)$
- Ordered Linked Lists
	- Lookups are $O(n)$
	- Inserting requires an $O(n)$ lookup and an $O(1)$ insert for $O(n)$
	- Removing takes an $O(n)$ lookup and an $O(1)$ removal for $O(n)$
- Hash table
	- Lookups are $O(1)$
	- Inserting is $O(1)$
	- Removing is $O(1)$
## Interface
```c
#include <stdbool.h>
typedef struct set *Set;

/** Creates a new empty set */
Set SetNew(void);

/** Free memory used by set */
void SetFree(Set set);

/** Inserts an item into the set */
void SetInsert(Set set, int item);

/** Deletes an item from the set */
void SetDelete(Set set, int item);

/** Checks if an item is in the set */
bool SetContains(Set set, int item);

/** Returns the size of the set */
int SetSize(Set set);

/** Displays the set */
void SetShow(Set set);
```