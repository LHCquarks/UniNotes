---
tags:
  - Continence
---
## Overview
Sorted data is sometimes more useful/helpful than unsorted data. We need efficient algorithms to Sort data within data structures. 

Structures are sorted by a Key which determines what the order actually is. Generally keys are numbers or words.

Sorting Algorithms have three main properties (beyond worst-case time complexity), which dictate their usefulness for specific tasks:
- **In Place/ Out of Place**: A sorting algorithm is 'In place' if it sorts the given data structure within the given data structure (i.e. no new array is created to help sort the data) and otherwise, it is 'out of place'
- **Stable/Unstable**: For items with more than one 'key' or value, a sorting algorithm is 'stable' if it preserves the given order of multiple items with the same key, and 'unstable' otherwise
- **Adaptive/Non-Adaptive**: A sorting algorithm is adaptive if the state of the inputted array affects the behaviour of the algorithm, and non-adaptive otherwise (If the same steps are performed regardless of how sorted the inputted array is, the algorithm is non-adaptive).
	-  Note that it must have a time complexity difference *not* just be constant time faster

## Comparison Based Sorting Algorithms
Comparison-Based Algorithms must have a lower bound of $O(nlog(n))$ worst-case time complexity.
### Elementary Sorting Algorithms:
- [[Selection Sort]]
- [[Bubble Sort]]
- [[Insertion Sort]]
- [[Shell sort]]
### Divide-and-Conquer Sorting Algorithms:
Divide and Conquer Sorting Algorithms breaks the problem into sub problems, which are solved recursively and then combined
- [[Merge Sort]]
- [[Quick Sort]]
### ADT-Based Algorithms:
- [[Heap Sort]]
## Non-Comparison Based Sorting Algorithms
- [[Radix Sort]]
- [[Key-indexed counting sort]]

## Time complexity
### Cases to consider
When imputed data is:
- Random order
- Sorted order
- Reverse sorted order
what is the time complexity?
### What operations do we care about?
When sorting items, sometimes we care about some factors more than others. Bellow are the operations we care about:
- Number of items $n$
- number of comparisons $C$
- number of items swapped $S$

## Comparison

| Algorithm                     | In-Place                           | Stable                             | Adaptive                           | Time Complexity |
| ----------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- | --------------- |
| [[Selection Sort]]            | <input type="checkbox" checked/>   | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> | $O(n^2)$        |
| [[Bubble Sort]]               | <input type="checkbox" checked/>   | <input type="checkbox" checked/>   | <input type="checkbox" checked/>   | $O(n^2)$        |
| [[Insertion Sort]]            | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> |                 |
| [[Shell Sort]]                | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> |                 |
| [[Merge Sort]]                | <input type="checkbox" unchecked/> | <input type="checkbox" checked/>   | <input type="checkbox" unchecked/> | $O(n\log n)$    |
| [[Quick Sort]]                | <input type="checkbox" checked/>   | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> | $O(n\log n)$    |
| [[Heap Sort]]                 | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> |                 |
| [[Radix Sort]]                | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> |                 |
| [[Key-indexed Counting Sort]] | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> | <input type="checkbox" unchecked/> |                 |
