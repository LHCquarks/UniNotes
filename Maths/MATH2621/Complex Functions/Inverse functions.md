## The problem
Non one-to-one functions are hard to make a proper inverse for.

If we get given a point that could have resulted from many different inputted values should our inverse function give back all of them or just one? If we give back only one which one?

## Solutions
There are two solutions to this problem...

### Multi values inverse function
Multi valued inverse functions give back all the points that could have generated a certain output at once. 

We usually denote these functions with a lowercase letter at the start.

#### Example:
$$
\begin{align}
\arg(i) &= \frac{\pi}{2}, \frac{\pi}{2} + 2\pi, \frac{\pi}{2} - 2\pi, \frac{\pi}{2} + 4\pi, \frac{\pi}{2} - 4\pi, ...
\end{align}
$$
### Restricted Domains
We can also restrict the domain of our function to get a particular result. 

The main set of results is typically called the principle branch and we denote functions like this with a capital letter.
#### Example:
$$
\begin{align}
\text{Arg}(i) &= \frac{\pi}{2}
\end{align}
$$
We can also denote we are referring to the principle branch of the single valued function by writing **PV** for principle value as such
$$
\begin{align}
\text{PV } w^{1/2} = \begin{cases} |w|^{1/2}e^{iArg(w)/2} &\text{if } w\not= 0 \\
0 &\text{if } w= 0
\end{cases}
\end{align}
$$
## Branch cuts
Branch cuts occur when we restrict a domain maximally. This means at the edges of our domain have the same value and so will map to the same value. 

This edge is our branch cut and generally results in the function becoming discontinuous at the edge.