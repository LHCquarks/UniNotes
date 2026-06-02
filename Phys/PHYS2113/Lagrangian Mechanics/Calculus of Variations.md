## Basic optimization
Given a function $f(x)$ we already know how to find it's maximum and minimum:
- solve $f'(x) = 0$
- test for $f''(x_0)$ to find the nature of the turning point
And we even know how to do this for the multivariable case and even with constraints with Lagrange multipliers.
## The Goal
The goal of the calculus of variations is to find a function $f(x)$ that extreme-izes an integral:
If we have
$$
\begin{align}
I[f] = \int_a^b f(x) dx
\end{align}
$$
then we want
$$
\begin{align}
\frac{dI}{df} = 0
\end{align}
$$
