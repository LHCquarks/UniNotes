---
tags:
  - In-Place
  - Stable
  - Adaptive
  - SortingAlgorithm
---
## Overview
- Bubble sort makes passes from left to right, switching any out-of-order adjacent items as it comes across them.
- The name 'bubble sort' comes from the fact that items 'bubble up' until they reach a larger item.
- The algorithm stops if no swaps are made in a pass (which is when the array is sorted).
- Due to the nature of bubble sort, the data is sorted in reverse, because after each pass, the greatest unsorted element bubbles up to its correct slot.
## Properties
Bubble sort is:
- **In place**
- **Stable**
- **Adaptive**
## Implementation
```c
void bubbleSort(int items[], int lo, int hi) {
	for (int i = hi; i > lo; i--) { 
		bool sorted = true;
		for (int j = lo; j < i; j++) {
			if (items[j] > items[j+1]) {
				swap(items, j, j + 1);
				sorted = false;
			}
		}
		if (sorted) break;
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
Let $n$ be the number of items in the array, and let the array be in the worst-case (decreasing order).
### Comparisons
#### Worst case
The first pass makes $n - 1$ comparisons, the second makes $n-2$, the third $n-3$, and so on.

Added together these produce the $n$th triangular number which is given by the formula $\frac{n(n-1)}{2}$.

Taking the asymptotic run time we get $C = O(n^2)$
#### Average case
In random order this is still true as the runtime becomes $\frac{1}{4}n(n-1)$  which is still $C = O(n^2)$
#### Best case
If the array is already sorted the algorithm only does one pass hence we $C = O(n)$ which makes bubble sort **adaptive**
### Swaps
#### Worst case
In the worst case the array is in reverse order. This leads to the algorithm making $n-1$ swaps on the first pass through, $n-2$ on the second and so on.

These are the triangular number so $S = \frac{1}{2} n(n-1) = O(n^2)$
#### Average case
idk
#### Best case
In the best case the array is already sorted resulting in no swaps occurring.

This means $S = 0 = O(1)$
## Animation
![[Bubble Sort Animation.gif]]