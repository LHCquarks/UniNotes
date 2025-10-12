## Searching algorithms
### Linear search
Here we check the first number then move to the next and so on
#### Time complexity
This is $O(n)$

### Binary search
If the array is sorted than we can use binary search.
1. First we index into the middle of the array and compare if the number is larger or smaller than the middle number
2. If it is larger we will then do the same but with the lower half of the array
3. If it is smaller we will do the same but with the upper half of the array
#### Implementation

```C
int binarySearch(int val, int *arr, int low, int heigh);

int binarySearch(int val, int *arr, int low, int heigh) {
	int mid = (low + heigh) / 2;
	int curr = arr[mid];
	// Base case
	if (val == curr) {
		return mid;
	} 
	// Recursive case
	if (val < curr) {
		return binarySearch(val, arr, low, mid - 1);
	} else {
		return binarySearch(val, arr, mid + 1, heigh);
	}
}
```

#### Time complexity
This is $O(\log_2(n)) = O(\log(n))$
## Finding common elements
Assuming there are no duplicate elements how many common elements in each array
### Implementation
```C
int common(int *a, int *b, int sizeA, int sizeB) {
	int count = 0;
	for (int i = 0; i < sizeA; i++) {
		for (int j = 0; j < sizeB; j++) {
			if (a[i] == b[j]) {
				count++;
			}
		}
	}
	return count;
}
```
### Time complexity
This is $O(nm)$

