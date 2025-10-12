## Overview
Radex sort requires us to decompose our keys into smaller parts.
Eg:
$123 \rightarrow 1, 2, 3$,
"abc" $\rightarrow$ "a", "b", "c"

We then need to make our keys all the same length by padding them at the front

We then go through each part of our key from the last part to the first part and for each perform the following steps:
- Place each key into arrays that match the small component of the key
- Start from the first array and place everything back into the original array preserving the order

Radex sort is called that because the key can be through of as a "radius".

## Implementation
```c

```


## Complexity Analysis
Radex sort is $O(m(n + R))$ where $m$ is the number of components in each key and $R$ is the number of components in each key

## Animation
