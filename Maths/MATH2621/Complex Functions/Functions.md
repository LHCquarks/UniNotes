## What is a function
It is a machine that takes something/s in and spits something out.
### Domain
The domain is what we are allowed to put into the function. If not specified we usually consider the largest reasonable domain
### Co-domain
This is the set of all possible outputs of the function + some more
### Range
The set of all possible outputs of the function
## Complex function
This is when we allow the domain and range to be apart of the complex numbers
### Examples
$f(z) = Re(z)$
$f(z) = |z|$

## Decomposition
### Cartesian
All complex functions $f(z)$ can be decomposed into 2 real functions, $u(x,y)$ and $v(x,y)$ with $$f(x+iy) = u(x,y) + iv(x,y) \tag{1}$$

This decomposition will be important as we will be able to apply theorems of real functions to complex functions.
### Polar
Sometimes it is easier to decompose complex functions into real and imaginary functions that depend upon polar coordinates like so
$$
\begin{align}
f(z) = u(r, \theta) + iv(r, \theta) \tag{2}
\end{align}
$$
where $z = re^{i\theta}$.
This can also be a more insightful representation of the function especially if the function has some sort of angular symmetry
#### Example
$$
\begin{align}
e^z &= e^{r\cos\theta + ir\sin\theta} \\
&= e^{r\cos\theta}(\cos(r\sin\theta) + i\sin(r\sin\theta)) \\
\implies u(r, \theta) &= e^{r\cos\theta}\cos(r\sin\theta)\\
v(r,\theta) &= e^{r\cos\theta}\sin(r\sin\theta)
\end{align}
$$


