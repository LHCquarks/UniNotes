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

