---
tags:
  - Continence
---
## Abstraction
Abstraction is the process of hiding or generalizing the details of an object or system to focus on its high-level meaning or behavior. A great example of this is the process of using pedals and a steering wheel to drive a car, or using a remote control to operate a tv.

## Abstract Data Types
An abstract data type is a conceptual model that defines a set of operations for a data structure without specifying how these operations are implemented or how data is stored in memory.

The user/customer is given a set of functions associated with the data type which they can use. They cannot **break abstraction** (directly manipulate with data), but can only use the functions given to them.

Example:
- **[[Stacks|Stack]]**: A stack is a linear collection of items with main operations:
    - Push `int`: Adds an item to the top of the stack
    - Pop: Removes the item at the top of the list and returns it
    - Peek: View the item at the top of the stack
    - Size: Get the number of items in the stack
    
    In this example, the user can only use Push, Pop, Peek, and get the Size from the stack, but they cannot manipulate or view any other data from the stack.

### Interface and Implementation
The set of operations provided by an ADT is called the interface. An interface must clearly describe the behavior of each operation, and the conditions under which each operation can be used. The implementation is where all the code is written.

Users of the ADT do not see the implementation. They can only interact with the interface. So, they cannot deference pointers or take/modify data from the implementation. They can only use the functions given to them in the interface.

Using abstract data types in c, we will have the implementation in a .c file, the interface in a .h file, and testing in another .c file. List all files in compilation.

### Naming Convention
- ADTs are defined in files whose names start with an uppercase letter
    - For example, the Stack ADT:
        - The interface is defined in Stack.h
        - The implementation is defined in Stack.c
- ADT interface function names are in PascalCase like `StackNew()` and begin with the name of the ADT

### ADT List: 
- [[Stacks]]
- [[Queues]]
- [[Sets]]
- [[Multiset]]
- [[Map]]
- [[Binary Search Trees]]
- [[Graphs]]
- [[Heaps]] and [[Priority Queues]]
- [[Tries]]

## Aliases
- `#ifndef` -> If not Defined
- `typedef` -> define a new type