Suppose that $\Omega$ is a simply connected domain in $\mathbb C$, that $f\in H(\Omega)$, that $\Gamma$ is a simple closed contour in $\Omega$ and that $w \in \text{Int}(\Gamma)$. Then 
$$
\begin{align}
f(w) = \frac{1}{2\pi i}\int_\Gamma \frac{f(z)}{z-w}dz
\end{align}
$$
## Example use case
Say we wanted to evaluate
$$
\begin{align}
\int_\Gamma \frac{\sin(z)}{z}dz \\
\end{align}
$$
at $z = 0$. Then we get that
$$
\begin{align}
\sin(z) &= \frac{1}{2\pi i}\int_\Gamma \frac{\sin(z)}{z - 0}dz \\
\int_\Gamma \frac{\sin(z)}{z}dz &= 2 \pi i\sin(0) = 0\\
\end{align}
$$
## Corollary
For integrals of the form
$$
\begin{align}
\int_\Gamma \frac{f(z)}{z-w}dz &= \int_\Delta \frac{f(z)}{z-w}dz
\end{align}
$$
### Mean value formula

## Generalized Cauchy Integral formula
With the same setup as the Cauchy Integral formula we get
$$
\begin{align}
f^{(n)}(w) = \frac{n!}{2\pi i}\int_\Gamma \frac{f(z)}{(z-w)^{n + 1}}dz
\end{align}
$$