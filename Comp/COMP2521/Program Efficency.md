How efficient are algorithms?
Can we measure this independently of the hardware used?

## Cases
### What is the best-case performance
Not very good because how often will this occur?
### Average performance
It is kinda hard to find this "average case"

### Worst case performance
This is the best because it is fairly easy to find but will give a useful number
## Time complexity
The amount of time a algorithm will take to run as a function of the input size of the program
### Methods to measure the time complexity
#### Empirically
Time it and plot results.

You can do this with
```C
#include <time.h>
#include <stdio.h>

int main(void) {
	clock_t start = clock();
	// Do main function
	
	
	clock_t end = clock();
	printf("%d", (double)(end - start) / CLOCKS_PER_SECOND);
}
```

However, this time will differ between hardware and languages so this might not be accurate between trials
#### Theoretically
Figure out the number of steps the program will take to solve a problem as a function of the input size and this should roughly map to the time spent.

### Primitive operations
Primitive operations are basic actions that we assume take constant time.
These are:
- Assignment
- Indexing into an array
- Calling / returning from a function
- Evaluating an expression
- incrementing and decrementing an variable
#### Example
How many primitive operations are there in this line of code
```C
for (int i = 0; i < n; i++)
```

Here `int i = 0` is called once,
`i < n` is called n + 1 times
`i++` is called n times

so there are `2n + 2` operations
### Asymptotic analysis
In general we do not care about smaller terms in the runtime, instead we only care about the Asymptotic time complexity.

This mean we get rid of lower order terms.

We also get rid of constant terms as the relative size between inputs does not change with it.

## Notation
We can denote the full time complexity as $T(n)$ but when talking about asymptomatic run time we use Big O notation where the asymptotic run time is placed in the brackets after $O$

### Example
$$
T(n) = n^2 + 3n - 2 \implies O(n^2)
$$

## Categories
### Single inputs
- Constant: 1
- logarithmic: $\log(n)$
- linear: $n$
- nlog(n): $n\log(n)$ 
- quadratic: $n^2$
- cubic: $n^3$
- exponential: $s^n$
- factorial: $n!$
### Two inputs
- $O(n+m)$
- $O(nm)$
- $O(\max(n,m))$
- $O(\min(n,m))$

