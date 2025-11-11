A singularity is any point where a function is not differentiable.

A point $z_0$ is called an **Isolated singularity** if the function $f$ is such that $f \in \text H (\text B(z_0, r))$ and $f$ is not differentiable at $z_0$.

We can further classify **isolated singularities** by expanding the function into it's Laurent Series.
The singularity is called a:
- <span style="color:aquamarine">essential singularity</span> if there is infinity many $c_n \not = 0$ for $n \in \mathbb Z^-$
- <span style="color:red">removable singularity</span> if there are no $n \in \mathbb Z^-$ such that $c_n \not = 0$
- <span style="color: DodgerBlue">pole</span> if there are finitely many terms with a negative power. In this case the largest of these terms $-m$ is the order of the pole and we say $f$ has a <span style="color:DodgerBlue">pole of order m</span>

## Examples
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
We get that all the following statements are equivalent for a function $f\in\text H(\text B^\circ(z_0, R))$ that has a pole at $z_0$ of order $M$ and can be expressed by the Laurent Series
$$
\begin{align}
f(z) = \sum_{n = -\infty}^\infty c_n (z - z_0)^n
\end{align}
$$
1. $c_n = 0$ for all $n < -M$ and $c_{-M} \not = 0$
2. there exists a function $F \in \text H(\text B (z_0, R))$ such that $f(z) = (z - z_0)^{-M}F(z)$ and $F(z_0) \not = 0$
3. $\lim_{z \rightarrow z_0} (z- z_0)^Mf(z)$ exists in $\mathbb C \backslash {0}$
4. there exists $C \in \mathbb R^+$ and $r \in (0, R)$ such that $|f(z)| \le C|z - z_0|^{-M}$ for all $z \in \text B^\circ(z_0, r)$
### Picard's theorem
If $f$ has an essential singularity at $z_0$, then for all $\delta > 0$ , the set $\mathbb C \backslash f(\text B^\circ (z_0, \delta))$ has at most one element.
## Lhopital's rule
Lhopital's rule holds in the complex case and so can be used to easily find the nature of a singularity:
Find the type of singularity of $f(z)  = (1 - \cos(z))^2 / z$
$$
\begin{align}
\lim_{z \rightarrow 0} f(z) &= \lim_{z \rightarrow 0} \frac{(1-\cos(z))^2}{z} \\
&= \lim_{z \rightarrow 0} \frac{(1-\cos(z))\sin(z)}{1} \\
&= 0
\end{align}
$$
so $f(z)$ has a <span style="color:red">removable singularity</span> that is a zero