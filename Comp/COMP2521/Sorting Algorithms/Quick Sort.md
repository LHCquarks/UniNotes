---
tags:
  - SortingAlgorithm
  - Unstable
  - In-Place
  - Non-Adaptive
---
## Quick Sort
## Overview
Quick Sort picks one of the items in the array to be a pivot, and puts every smaller element to the left, and every larger item to the right of the pivot. The left and right partitions are then recursively sorted

## Properties
Quick Sort is:
- **Unstable**
- **In Place**
- **Non-Adaptive**
## Implementation
```c
void quickSort(int items[], int lo, int hi) {
	if (lo >= hi) return;
	int pivotIndex = partition(items, lo, hi);
	
	quickSort(items, lo, pivotIndex-1);
	quickSort(items, pivotIndex+1, hi);
}

int partition(int items[], int lo, int hi) {
	int piviot = items[lo]
	int left = lo + 1;
	int right = hi;
	
	while (left < right) {
		while (left < right && items[left] <= pivot) left++;
		while (left < right && items[right] <= pivot) right--;
		
		if (left == right) break;
		swap(items, piviot, left - 1);
	}
	
	return left - 1;
}
```


## Complexity Analysis
### Comparisons
#### Worst case
When we partition we make $n-1$ comparisons

We do the above for $n$ where each partition is one less than the previous. This is when the array is sorted or reverse sorted

Combining this makes $C = O(n^2)$
#### Best case
When we partition we make $O(n)$ comparisons

We do the above for each of the $\log_2(n)$ levels.

So the comparisons are $C=O(n\log(n))$

### Swaps
#### Worst case

#### Best case

## Smarter approaches
### Median of three
To limit ourselves from getting bad pivots we can use the Median-of-Three Quicksort where we:
- look at the first, last and middle element of the array

$O(nlog(n))$
The choice of pivot can greatly affect the time taken for the algorithm to complete. So, one approach is the Median-of-Three Quicksort:
- The median between the first, middle, and last element of the array is chosen to be the pivot
- Sorting continues normally

### Random partitioning
Instead of selecting a partition systematically we can use a rng to get a random index in our range.

We then swap number with the start of our partition then we run quick sort on it.

This makes it almost impossible to systematically develop a $O(n^2)$ seed.

### Other sorting algs
For small sequences quick sort is expensive.

Because of the extra overhead it is better to run other sorting algorithms like insertion sort when the size of the partition is low enough.

In general we use insertion sort when $n < 5$

## Animation



