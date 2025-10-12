## Recursion
- Works by breaking a problem down into smaller problems, and using their results to construct larger results
- In our functions we deal with 2 cases:
    - Base Case(s): The simplest, smallest version which can be directly solved
    - Recursive Case: A sub-problem of a certain size which can be solved using smaller cases
- Process of writing recursive code:
    1. Consider is '*How can I break this problem down into a smaller problem?*'
    2. Consider the base case and write it's solution
    3. Find the smaller sub-problem. Sometimes, there are natural choices for the sub-problem, like:
        - If the input is `x`, the natural choice for the sub-problem is `x-1`
        - If the input is a linked list, the natural choice for the sub-problem is usually the rest of the linked list without the head.
    4. Solve the problem, thinking '*assuming I have the answer to the sub-problem, how can I solve this problem?*'
- Example: Factorial
```c
int factorial(int num) {
	if (num == 0) {
		return 1; // Base Case
	} else {
		return num * factorial(num - 1); // Recursive Case
	}
}
```
- Recursive Problems call stack frames upon stack frames until the base case is reached, where it starts returning.
- When the recursive function is being continuously called it is called the **winding** phase
- When the recursive function is returning it is called the **unwinding** phase
- Operations that occur in the winding phase are called **Pre-order operations**
- Operations that occur in the unwinding phase are called **Post-order operations**
## Examples
### Length of a linked list
Write a recursive function to compute the length of a linked list.
#### Signature
```c
int listLength(struct node *l);
```
#### Solution:
```c
int listLength(struct node *l) {
	// Base Case
	if (l == NULL) {
		return 0;
	}
	// Recursive Case
	return 1 + listLength(l->next);
}
```
### Number of odd numbers in a linked list
Write a recursive function to count the number of odd numbers in a linked list.
#### Signature
```c
int listCountOdds(struct node *l);
```
#### Solution:
```c
int listCountOdds(struct node *l) {
	// Base Case
	if (l == NULL) {
		return 0;
	}

	// Recursive Case
	if (l->value % 2 == 0) {
		return 0 + listCountOdds(l->next);
	} else if (l->value % 2 == 1) {
		return 1 + listCountOdds(l->next);
	}
}
```

### Sorted linked list
Write a recursive function to check whether a list is sorted in ascending order.
#### Signature
```c
bool listIsSorted(struct node *l);
```
#### Solution
```c
bool listIsSorted(struct node *l) {
	// Base case
	if (l->next == NULL) {
		return True;
	}
	int curr = l->value;
	int nextVal = l->next->value;
	if (curr != nextVal) {
		return False;
	}
	// Recursive case
	return listIsSorted(l->next);
}
```
### Delete first occurrence
Write a recursive function to delete the first instance of a value from a linked list, if it exists. The Function should return a pointer to the beginning of the updated list.
#### Signature
```c
struct node *listDelete(struct node *l, int value);
```
#### Solution
```c
struct node *listDelete(struct node *l, int value) {
	struct node *next = l->next;
	// Base case
	if (l->value == value) {
		free(l);
		return next;
	}
	if (next == NULL) {
		return l;
	}
	// Recursive case
	l->next = listDelete(next, value);
	return l;
}
```

### Print items in reverse
Given a linked list, print the items in the list in reverse.
#### Signature
```c
void printList(struct node *l);
```
#### Solution
```c
void printList(struct node *l) {
	// Base case
	if (l == NULL) {
		return;
	}
	// Recursive case
	printList(l->next);
	printf("%d ", l->value);
	return;
}
```
### Second item
Given a linked list, print every second item.
#### Signature
```c
void printSecond(struct node *l);
```
#### Solution
```c
void printSecond(struct node *l) {
	// Base case
	if (l == NULL || l->next == NUL) {
		return;
	}
	// Recursive case
	prinf("%d ", l->value);
	printSecond(l->next->next);
}
```
### Item at index
Given a linked list and an index, return the value at that index.
#### Signature