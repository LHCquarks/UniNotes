## Algorithm properties

| Algorithm                 | Average time complexity | Best time complexity | Worst time Complexity | Stable |
| ------------------------- | ----------------------- | -------------------- | --------------------- | ------ |
| Bubble sort               | $O(n^2)$                | $O(n)$               | $O(n^2)$              | True   |
| Selection sort            | $O(n^2)$                | $O(n^2)$             | $O(n^2)$              | False  |
| Merge sort                | $O(n\log n)$            | $O(n\log n)$         | $O(n\log n)$          | True   |
| Naive quicksort           | $O(n\log n)$            | $O(n\log n)$         | $O(n^2)$              | False  |
| Median-of-three quicksort | $O(n\log n)$            | $O(n\log n)$         | $O(n^2)$              | False  |
| Bogosort                  | $O(2^n)$                | $O(n)$               | $O(2^n)$              | False  |

## Method
For each sorting algorithm we will follow the flow chart bellow.
### Flow chart
![[FlowChart.png]]
### Measuring relative time complexity
To measure the relative time complexity of each algorithm we conduct multiple (100) tests where $n$ ranges $10,000 - 100,000$ recording the time it took for the algorithm to run for each trial.

We then can take this data and plot it, comparing it to lines of best fit to find the time complexity.

To record the data I used the bellow bash script for random data:
```BASH
#!/bin/bash

increment=(100000-10000)/100

for ((n = 10000; n < 100000; n = n + increment)); do
	./gen $n R | time ./$1 > /dev/null
done
```
and the bellow bash script for sorted data:
```BASH
#!/bin/bash

increment=(100000-10000)/100

for ((n = 10000; n < 100000; n = n + increment)); do
	./gen $n A | time ./$1 > /dev/null
done
```

### Measuring stability
To measure stability we input random key value pairs (2 numbers side by side) and sort it with both the sorting algorithm we are investigating and a known stable sorting algorithm such as unix sort with the stable flag.

## Results
Tables of data for each test can be found the appendix
### Algorithm A
#### Random data
![[SortA random.png]]
As can be seen sortA is on average $O(n^2)$ meaning it is either 
**Bubble Sort** or **Selection Sort**
#### Sorted data
![[SortA sorted.png]]
As can be seen sortA has a complexity of $O(n^2)$ even when the data is already sorted. This means it is not **Bubble Sort** because **Bubble Sort** has a $O(n)$ complexity for sorted data.

This means that sortA must be **Selection Sort**
### Algorithm B
#### Random data
![[SortB random.png]]
As shown above sortB has an average complexity of $O(n\log n)$ meaning it must be one of:
- **Merge Sort**
- **Naive Quicksort**
- **Median-of-three Quicksort**
#### Sorted data
![[SortB sorted.png]]
As can be seen, for sorted data, sortB had a complexity of $O(n^2)$ eliminating both **Median-of-three Quicksort** and **Merge Sort**.

This leaves us with sortB being **Naive Quicksort**.

## Appendix
### Sort A random data
```csvtable
source: sortArand.txt
```
### Sort A sorted data
```csvtable
source: sortAsorted.txt
```
### Sort B random data
``` csvtable
source: sortBrand.txt
```

### Sort B sorted data
``` csvtable
source: sortBsorted.txt
```
