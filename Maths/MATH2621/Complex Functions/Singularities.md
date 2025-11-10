A singularity is any point where a function is not differentiable.

A point $z_0$ is called an **Isolated singularity** if the function $f$ is such that $f \in \text H (\text B(z_0, r))$ and $f$ is not differentiable at $z_0$.

We can further classify **isolated singularities** by expanding the function into it's Laurent Series.
The singularity is called a:
- <span style="color:aquamarine">essential singularity</span> if there is infinity many $c_n \not = 0$ for $n \in \mathbb Z^-$
- <span style="color:red">removable singularity</span> if there are no $n \in \mathbb Z^-$ such that $c_n \not = 0$
- <span style="color: DodgerBlue">pole</span> if there are finitely many terms with a negative power. In this case the largest of these terms $-m$ is the order of the pole and we say $f$ has a <span style="color:DodgerBlue">pole of order m</span>

## examples
Take 
$$
\begin{align}
f(z) = \frac{\sin(z)}{z}
\end{align}
$$
this function's Laurent Series around $0$ has no negative terms and so $0$ is a <span style="color:red">removable singularity</span> of $f$

Take
$$
\begin{align}
f(z) = \frac{1}{z^3 - z}
\end{align}
$$

the Laurent Series around $0$ has exactly one negative power ($-z^{-1}$) so $0$ is a <span style="color:DodgerBlue">pole of order 1</span>
## Singularity theorems
We get that all the following statements are equivalent for a function $f\in\text H(\text B^\circ(z_0, R))$ that can be expressed by the Laurent Series
$$
\begin{align}
f(z) = \sum_{n = -\infty}^\infty c_n (z - z_0)^n
\end{align}
$$
1. $c_n = 0$ for all $n < 0$
2. $\lim_{z \rightarrow z_0} f(z)$ exists in $\mathbb C$ and $f$ can be extended to a holomorphic function on $\text B(z_0, R)$
3. there exists $C \in \mathbb R^+$ and $r \in (0, R)$ such that $|f(z)| \le C$ for all $z \in \text B^\circ(z_0, r)$

