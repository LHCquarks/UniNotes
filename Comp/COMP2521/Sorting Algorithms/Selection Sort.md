---
tags:
  - SortingAlgorithm
  - In-Place
  - Unstable
  - Non-Adaptive
---
**Preamble**
Selection sort, while not limited to arrays, works best on arrays due to their indexing. The explanation and examples of selection sort will assume the given data is in the form of an array.

## Overview
Selection Sort is an algorithm which takes in an array in random order, and builds up the sorted array from the first entry by swapping the **smallest** unsorted element with the **first** unsorted element.. This means each 'step', the size of the sorted partition increases by 1.

Selection Sort is:
- **In-Place** (Values are sorted within the given array)
- **Unstable** (Does not preserve the given order of multiple items with the same key)
- **Non-Adaptive** (The state of the inputted array does not affect the algorithm's performance/behaviour)

## Implementation
```c
void selectionSort(int items[], int lo, int hi) {
		// lo and hi are the indices you want to sort between (INCLUSIVE)
	for (int i = lo; i < hi; i++) {
		int min = i;
		for (int j = i + 1; j <= hi; j++) {
			if (items[j] < items[min]) {
				min = j;
			}
		}
		swap(items, i, min);
	}
	return;
}

void swap(int items[], int i, int j) {
	int temp = items[i];
	items[i] = items[j];
	items[j] = temp;
	return;
}
```

## Complexity Analysis
Let $n$ be the number of items in the array.

### Comparisons

The first pass makes $n - 1$ comparisons, the second makes $n - 2$, the third $n - 3$, and so on.

This is just the $n$th triangle number given by the formula $\frac{n(n-1)}{2}$
 
So the overall worst-case time complexity, taking out the constant and lower-order terms, is $C = O(n^2)$.
### Swaps
For each iteration there is only one swap that occurs. Hence the cost in swaps is $S = n - 1 = O(n)$
## Animation
The animation below is shows the process of selection sort, where the height of the bar represents the the key which is being used to sort the data. Note that here there are no duplicate data values and there is one value for each integer from $1$ to $n$, so this animation may appear simplified.
![[sorting.gif]]