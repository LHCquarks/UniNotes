## Definition
A power series is an expression that takes the form
$$
\begin{align}
\sum_{n=0}^\infty a_n(z - z_0)^n
\end{align}
$$
where:
- $z$ is a complex variable
- $z_0$ is a complex number we refer to as the *center*
- $a_n$ are the coefficients of each index
- we make the assumption that for any number $z$, $z^0 = 1$ even when $z = 0$
## Convergence
For every power series we have a $\rho \in [0, \infty]$ called the *radius of convergence* such that when
- $|z - z_0| < \rho$ then the power series converges
- $|z - z_0| > \rho$ then the power series does not converge
- $|z - z_0| = \rho$ we don't know if it converges or not. More work is required

We define $\rho$ as:
$$
\begin{align}
\rho &= (\limsup_{n\rightarrow \infty}|a_n|^{1/n})^{-1} \\
&= (\lim_{k\rightarrow\infty} \sup_{n \ge k} |a_n|^{1/n})^{-1}
\end{align}
$$
### Ratio test
We can use the ratio test to find $\rho$ which says:

If
$$
\begin{align}
\lim_{n\rightarrow \infty} \frac{|a_n|}{|a_{n+1}|}
\end{align}
$$
exists or is $+\infty$ then it equals $\rho$

### Root test
We can also use the root test to find $\rho$ which says:

If
$$
\begin{align}
\lim_{n\rightarrow\infty} \frac{1}{|a_n|^{1/n}}
\end{align}
$$
exists or is $+\infty$ then it equals $\rho$

### Sterlings formula
this formula might be useful for the above tests:
$$
\begin{align}
\lim_{n\rightarrow \infty}\frac{(n!)^{1/n}}{n/e} = 1
\end{align}
$$
## Algebra of power series
For two power series $f(z) = \sum_{n=0}^\infty a_n(z - z_0)^n$ and $g(z)= \sum_{n=0}^\infty b_n(z - z_0)^n$:
$$
\begin{align}
\sum_{n=0}^\infty c \ a_n(z - z_0)^n &= cf(z) \tag{1} \\
\sum_{n=0}^\infty (a_n + b_n)(z - z_0)^n &= f(z) + g(z) \tag{2} \\
\end{align}
$$
and letting
$$
\begin{align}
c_n = \sum_{j=0}^n a_j b_{n-j}
\end{align}
$$
we get that:
$$
\begin{align}
\sum_{n=0}^\infty c_n(z - z_0)^n &= f(z)g(z) \tag{3}
\end{align}
$$
## Derivatives
Within the radius of convergence of a power series it is differentiable with the formula:
$$
\begin{align}
f'(z) = \sum_{n=1}^\infty a_n n (z-z_0)^{n-1} = \sum_{m=0}^\infty a_{m+1} (m+1) (z-z_0)^m
\end{align}
$$
It follows that a power series is infinity differentiable with the general formula:
$$
\begin{align}
f^{(k)}(z) = \sum_{n = k}^\infty n(n-1)...(n-k+1)a_n(z-z_0)^{n-k}
\end{align}
$$
Test