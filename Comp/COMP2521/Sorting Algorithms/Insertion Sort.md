---
tags:
  - Adaptive
  - In-Place
  - Stable
  - SortingAlgorithm
---
## Overview
Insertion sort builds up a sorted array on the left hand side. We then *insert* items into the sorted array so that the sorted array remains sorted

We *insert* items into their correct spot by looping from the end of the sorted array and swapping items with the new item until we find it's spot
## Properties
Insertion Sort is:
- **Adaptive**
- **In-Place**
- **Stable**
## Implementation
```c
void insertionSort(int items[], int lo, int hi) {
	for (int i = lo; i <= hi; i++) {
		for (int j = i; j > lo; j--) {
			if (items[j] < items[j - 1]) {
				swap(items, j, j -1);
			} else break;
		}
	}
}
```
## Complexity Analysis
### Comparisons
#### Worst case
The worst case is if the array is in reverse sorted order

In this case we get the triangle numbers so $C = O(n^2)$
#### Average case
The average case still leads to a $C = O(n^2)$
#### Best case
The best case is if the array is already sorted.
In this case we get that $C = O(n)$
### Swaps
#### Worst case
The worst case is if the array is reverse sorted.
These are the triangle numbers so $S = O(n^2)$
#### Best case
The best case is a fully sorted array where no swaps will occur. 
This means $S = 0 = O(1)$

## Animation
![[Insertion Sort Animation.gif]]