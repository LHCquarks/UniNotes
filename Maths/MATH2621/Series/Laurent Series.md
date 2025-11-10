The Laurent Series of a function is a generalization of the Taylor series of a function allowing negative powers.

## Definition
A Laurent Series is defined on the annulus (ring) $\text A = \{z\in \mathbb C: R_1 < |z - z_0| < R_2\}$ where $R_1 < r < R_2$, $f \in \text H(\text A)$ then:
$$
\begin{align}
f(w) = \sum_{n = -\infty}^\infty c_n(w - z_0)^n
\end{align}
$$
Where
$$
\begin{align}
c_n = \frac{1}{2 \pi i} \int_{\partial B(z_0, r)} \frac{f(z)}{(z-z_0)^{n+1}} dz
\end{align}
$$
## Examples
Find the Laurent Series of 
$$
\begin{align}
f(z) &= \frac{1}{z(z^2 - 1)}
\end{align}
$$
Using PFD we see:
$$
\begin{align}
f(z) &= \frac{-1}{z} + \frac{1/2}{z - 1} + \frac{1/2}{z+1}
\end{align}
$$The two possible annuls are $\{z\in \mathbb C: 0 < |z - z_0| < 1\}$ and  $\{z\in \mathbb C: 1 < |z - z_0| < \infty\}$.
Within the first we get:
$$
\begin{align}
f(z) &= \frac{-1}{z} - \frac{1}{2}\sum_{n = 0}^\infty z^n + \frac{1}{2} \sum_{n=0}^\infty (-1)^nz^n \\
&= -\frac{1}{z} + (z + z^3 + z^5 + ...)
\end{align}
$$
and within the second we get:
$$
\begin{align}
f(z) &= -\frac{1}{z} + \frac{1}{2z} \frac{1}{1- 1/z} + \frac{1}{2z} \frac{1}{1 + 1/z} \\
&= -\frac{1}{z} + \frac{1}{2z} \sum_{n = 0}^\infty \left(\frac{1}{z}\right)^n + \frac{1}{2z} \sum_{n = 0}^\infty (-1)^n\left( \frac{1}{z}\right)^n \\
&= -z^{-1} + z^{-1} (1 + z^{-2} + z^{-4} + ...) \\
&= z^{-1} (z^{-2} + z^{-4} + ...) \\
&= z^{-3} + z^{-5} + z^{-7} + ... \\
\end{align}
$$
