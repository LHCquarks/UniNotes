The Laurent Series of a function is like the Taylor series of a function but we allow negative powers

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
