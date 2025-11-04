Just as was in real calculus the Taylor series is defined by
$$
\begin{align}
\sum_{n=0}^{\infty} \frac{f^{(n)}(z_0)}{n!} (z-z_0)^n
\end{align}
$$
This power series is equal to $f$ for all values of $z \in \text B (z_0, \rho)$.
## Radius of convergence
We find that the radius of convergence of any Taylor series is the distance between $z_0$ to the closest singularity of $f$ or the closest instance of $f$ not being holomorphic!
## Finding the Taylor Series
Generally we can find the Taylor series through algebraic manipulation into **exponentials** and **geometric series**

## Examples
Find the Maclaurin series of
$$
\begin{align}
f(z) &= \begin{cases} \frac{\sin(z)}{z} & z \not= 0 \\ 1 & z = 0\end{cases}
\end{align}
$$
We know that
$$
\begin{align}
\sin(z) = \sum_{n=0} ^\infty \frac{(-1)^n}{(2n+1)!} z^{2n + 1}
\end{align}
$$
therefore:
$$
\begin{align}
f(z) = \sum_{n=0} ^\infty \frac{(-1)^n}{(2n+1)!} z^{2n}
\end{align}
$$
