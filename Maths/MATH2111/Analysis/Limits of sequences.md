## Metrics
### Definition
To define the continuity of a **curve** or **surface** we need to define what we mean when we say two points are close to one another. For this we need a **metric**.

**Metrics** are defined as functions $d: \mathbb R^n \times \mathbb R^n \rightarrow [0, \infty)$ that for all $x, y, z \in \mathbb R^n$ satisfy:
- $d(x, y) = 0 \iff x = y$
- $d(x, y) = d(y, x)$
- $d(x, y) \le d(x, z) + d(z, y)$
### Examples
Some common examples of **metrics** include:
- The **Euclidean** metric: $d_2(x, y) = \sqrt{\sum_{k=0}^n |x_k - y_k|^2}$
- The **Taxicab / Manhatten** metric $d_1(x, y) = \sum_{k=0}^n |x_k - y_k|$
- The **p**-metric $d_p(x, y) = \left(\sum_{k = 0}^n |x_k - y_k|^p\right)^{1/p}$
- The **Chebyshev** metric $d_\infty(x, y) = \max_{1 \le k \le n} |x_k - y_k|$
- The **Discrete** metric which is defined by:
$$
\begin{align}
d(x, y) =
\begin{cases}
 1 &\text{if } x\not=y \\ 0 &\text{if } x = y
\end{cases}
\end{align}
$$
Further given a **metric** $d(x, y)$  it is possible to construct another **metric** $\delta(x, y)$ by:
$$
\begin{align}
\delta(x, y) &= \frac{d(x, y)}{1 + d(x, y)}
\end{align}
$$

### (strongly) Equivalent metrics
We say that two **metrics** $d, \delta$ defined on $\mathbb R^n$ are **strongly equivalent** if there a constants $c, C > 0$ such that for all $x, y \in \mathbb R^n$:
$$
\begin{align}
cd(x, y) \le \delta(x, y) \le Cd(x, y) \\
\end{align}
$$
#### Examples
- $d_p$ is **strongly equivalent** to $d_q$ for all $p, q \in [1, \infty]$ on $\mathbb R^n$
- The discrete metric is **not** equivalent to $d_p$ for any $p \in [1, \infty]$ on $\mathbb R^n$
## Convergent and Cauchy Sequences
### Definition of convergent sequences
Suppose that $d$ is a **metric** on $\mathbb R^n$.
A sequence $\{x_k\}_{k=1}^\infty$ in $\mathbb R^n$ is said to be **convergent** with respect to $d$ if:

There exists $x\in \mathbb R^n$ such that $\lim_{k\rightarrow \infty} d(x_k, x) = 0$.
### Uniqueness of a sequence's limit
Assume that the sequence $\{x_k\}_{k=1}^\infty$ converges to both $x$ and $x'$ on the metric $d$.

By the definition of the limit for all $\epsilon > 0$  we can find both $K$ and $K'$ such that for all $k$ larger than $K$ and $K'$ respectively we get:
$$
\begin{align}
d(x_k, x) &< \frac{\epsilon}{2} \\
d(x_k, x') &< \frac{\epsilon}{2}
\end{align}
$$
Now taking $k > \max(K, K')$ and adding the above equations we get $d(x_k, x) + d(x_k, x') < \epsilon$ which using the properties of **metrics** we simplify to:
$$
\begin{align}
0 &\le d(x, x') < \epsilon \\
\end{align}
$$
Now because $\epsilon$ was arbitrary we can make it arbitrarily small meaning $d(x, x') = 0$ which again using the properties of **metrics** means that $x = x'$. Therefore there is only one unique limit of a sequence.

### Definition of cauchy sequences
A **cauchy** sequence is one where elements get arbitrarily close to one another.
Mathematically we let $j, k > K$ then a sequence is **cauchy** if $\lim_{K \rightarrow \infty} d(x_j, x_k) = 0$.
Or in quantifiers:
$$
\begin{align}
\forall\epsilon>0 \ \ \ \ \exists K\in \mathbb Z^+ \ \ \ \ \forall j, k > K \ \ \ \ d(x_j, x_k) < \epsilon
\end{align}
$$
### Convergence $\implies$ Cauchy
If a sequence $\{x_k\}_{k = 1}^\infty$ is **convergent** with respect to $d$ then:
Let $K$ be such that $d(x_k, x) < \frac{\epsilon}{2}$ for all $k > K$ then if $j, k > K$ we have that:
$$
\begin{align}
d(x_j, x_k) &\le d(x_j, x) + d(x_k, x) \\
&< \frac{\epsilon}{2} + \frac{\epsilon}{2} \\
& = \epsilon
\end{align}
$$
Therefore $d(x_j, x_k) < \epsilon$  thus satisfying the definition of **cauchy**.

Further, taking the contrapositive of this, if a sequence is **not** **cauchy** then the sequence does **not** **converge**
### Cauchy in $d_2$ $\implies$ Convergent
This is not proven but is true

### Convergence under strongly equivalent metrics
Suppose that $\delta, d$ are **strongly equivalent** **metrics** on $\mathbb R^n$ and that $\{x_k\}_{k=1}^\infty$  is a sequence on $\mathbb R^n$.

We have that $\{x_k\}_{k=1}^\infty$ is **convergent** on $\delta$ if and **only** if it is **convergent** on $d$.
We also have the same fact for if the sequence is **cauchy**.
### Convergence of components
A sequence $\{x_k\}_{k=1}^\infty$ on $\mathbb R^n$ only **converges** on $d_2$ if and only if all of the sequences of components $\{x_k^{(i)}\}_{k=1}^\infty$ **converge**.

Because $d_2$ is **strongly equivalent** to $d_\infty$ the sequence converges iff
$$
\begin{align}
d_\infty(x_k, x) &< \epsilon \\
\max_{1 \le i \le n} \left|x_k^{(i)} - x^{(i)} \right| &< \epsilon
\end{align}
$$
Assuming that the sequence converges it is obvious that components must converge for the second inequality to hold

Going the other way we simply take the largest $K_i$ such that the second inequality holds and we can work backwards to find that the total sequence must hold.