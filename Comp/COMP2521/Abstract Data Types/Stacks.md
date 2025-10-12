## Overview
A stack is a collection of items such that that last item to enter is the first to leave (LIFO - Last in First Out). 
Some uses of this are:
- Web Browser History
- Text editor undo/redo
- Function calls
- Balanced brackets ({()}())

Stacks support the following operations:
- Push - add a new item to the top of the stack
- Pop - remove the topmost item from the stack
- Size - return the number of items in the stack
- Peek - get the topmost item on the stack without removing it

How to implement a stack?
- Arrays and linked lists can both efficiently implement a stack.

## Interface
```c
typedef struct stack *Stack

// Creates a new, empty Stack
Stack StackNew(void);

// Frees memory allocated for a Stack
void StackFree(Stack s);

// Adds an item to the top of a Stack
void StackPush(Stack s, Item item);

// Removes an item from the top of a Stack
// Assumes that the Stack is not empty
Item StackPop(Stack s);

// Gets the number of items in the Stack
int StackSize(Stack s);

// Gets the item at the top of the Stack
// Assumes that the Stack is not empty
Item StackPeek(Stack s);
```

## Time complexity
### Push
Normally inserting it is $O(1)$

Because reallocating occurs infrequently it is still $O(1)$ for an array
### Pop
Pop is only $O(1)$

