## Definition
Harmonic functions are defined as such:

Suppose that:
- $\Omega$ is an open subset of $\mathbb{R}^2$
- $u: \Omega \rightarrow \mathbb{R}$ is a function
- $u$ is twice **continuously** differentiable
We say that $u$ is **harmonic** in $\Omega$ if the Laplace equation holds:
$$
\begin{align}
\frac{\partial^2u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0
\end{align}
$$
## Finding harmonic functions
Suppose that a **Holomorphic** function $f: \mathbb{C}\rightarrow\mathbb{C}$ has cont second derivatives.

Then $f(x + iy) = u(x,y) + iv(x,y)$ where both $u$ and $v$ are **harmonic**

## Harmonic conjugates
If:
- $\Omega$ is a simply polygonally connected domain
- $u: \Omega \rightarrow \mathbb{R}$ is harmonic
then there exists a harmonic $v: \Omega \rightarrow \mathbb R$ such that $f = u + iv$ is holomorphic on $\Omega$.

This $v$ that satisfies this is called the **harmonic conjugate** of $u$

### Uniqueness of harmonic conjugates
On top of there always being a harmonic conjugate to a harmonic function, this function is unique up to a constant term.


