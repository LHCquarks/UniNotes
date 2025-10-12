---
tags:
  - SortingAlgorithm
  - Non-Adaptive
  - Stable
  - Out-Of-Place
---
## Overview
Merge sort splits the array into two roughly equal sized partitions, and recursively sorts both partitions. They are then merged together, sorting as they are merged.
## Properties
Merge sort is:
- **Non Adaptive**
- **Out of place**
- **Stable**
## Implementation
### Recursive implementation
```c
void mergeSort(int items[], int lo, int hi) {
	// High and low have crossed over -> we are at base case
	// Array of a single element is sorted
	if (lo >= hi) return; 
	int mid = (hi + lo) / 2;
	// Split array into two and sort those
	mergeSort(items, lo, mid); 
	mergeSort(items, mid + 1, hi);
	// Merge the two sorted list into a bigger sorted list
	merge(items, lo, mid, hi);
}

void merge(int items[], int lo, int mid, int hi) {
	// Make space for the bigger sorted list
	int *temp = malloc((hi - lo + 1) * sizeof(int));
	
	// Index into the first array
	int i = lo
	// Index into the second array
	int j = mid + 1
	// Index into the merged array
	int k = 0;
	// While we havent finnised copying any of the arrays
	while (i <= mid && j <= hi) {
		if (items[i] <= items[j]) {
			// copy the next element from the first array
			temp[k] = items[i];
			k++;
			i++;
		} else {
			// copy the next element from the second array
			temp[k] = items[j];
			k++;
			j++;
		}
	}
	// Copy Unfinished Segments
	while (i <= mid) temp[k++] = items[i++];
	while (j <= hi) temp[k++] = items[j++];
	
	// Copy segments into original array
	for (i = lo, k = 0; i <= hi; i++, k++) {
		items[i] = temp[k];
	}
	free(temp);
	return;
}
```
### Iterative implementation
This implementation first splits the array into pairs of length 1 arrays and merge those pairs together. 

After, It splits the array into pairs of length 2 arrays and applies the same merge procedure. 

It continues this until the entire array is sorted.
```C
void mergeSort(int items[], int lo, int hi) {
	// m represents the size of the groups we are sorting
	for (int m = 1; m <= hi - lo; m *= 2) {
		// i represents the ith pair we are sorting for
		for (int i = lo; i <= hi - m; i += 2*m) {
			int end = min(i + 2*m - 1, hi);
			merge(items, i, i + m - 1, end);
		}
	}
}

void merge(int items[], int lo, int mid, int hi) {
	// Make space for the bigger sorted list
	int *temp = malloc((hi - lo + 1) * sizeof(int));
	
	// Index into the first array
	int i = lo
	// Index into the second array
	int j = mid + 1
	// Index into the merged array
	int k = 0;
	// While we havent finnised copying any of the arrays
	while (i <= mid && j <= hi) {
		if (items[i] <= items[j]) {
			// copy the next element from the first array
			temp[k] = items[i];
			k++;
			i++;
		} else {
			// copy the next element from the second array
			temp[k] = items[j];
			k++;
			j++;
		}
	}
	// Copy Unfinished Segments
	while (i <= mid) temp[k++] = items[i++];
	while (j <= hi) temp[k++] = items[j++];
	
	// Copy segments into original array
	for (i = lo, k = 0; i <= hi; i++, k++) {
		items[i] = temp[k];
	}
	free(temp);
	return;
}
```
## Complexity Analysis
![[Pasted image 20250923092045.png]]
### Comparisons
No matter the case the algorithm does the exact same procedure and hence it is **non-adaptive**. 
#### Winding phase
In the winding phase we make $n-1$ splits over a total of $\log_2(n)$ levels.

No comparisons are made during this meaning that is $O(1)$ 
#### Unwinding phase
For each layer to be unwound we make at least $n/2$ comparisons.

Because there are $\log_2(n)$ layers this means we make $O(n\log(n))$ comparisons.

#### Total
Adding the *Winding phase* to the *Unwinding phase* we get $C = O(1) + O(n\log(n)) = O(n\log(n))$ 

#### Alternate complexity analysis
We have the recursive relation that:
$T(n) = aT(\frac{n}{b}) + f(n)$
Where:
- $a$ is the number of times the recursive function is called every iteration so $a = 2$
- $b$ is how much we cut down the size of the array between iterations so $b = 2$
- $f(n)$ is the non-recursive algorithm (merge) run every iteration so $f(n) \approx 2n$

The **Master Theorem** States, among other cases, that for a recursion relation of the above form, if $f(n) = n^c$ for some $c$ and $c = c_{rit}$ where $c_{rit} = \log_b(a)$ then in big $O$ notation the time complexity is
$O(n(\log(n))^c)$ .

In this case $c = 1$ and $c_{rit} = \log_2(2) = 1$ so the above case holds and $C = O(n(\log(n))^1) = O(n\log(n))$  

### Memory
#### Winding
During the winding phase constant memory is used so $O(1)$.
#### Unwinding
During the unwinding phase we must allocate $n$ units of memory for each layer hence we must allocate a total of $O(n\log(n))$ memory.
#### Total
Adding these two together we get that $M = O(n\log(n))$.
## Animation
![[Merge Sort Animation.gif]]