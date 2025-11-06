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
Suppose that a **holomorphic** function $f: \mathbb{C}\rightarrow\mathbb{C}$ has cont second derivatives.

Then $f(x + iy) = u(x,y) + iv(x,y)$ where both $u$ and $v$ are **harmonic**

## Harmonic conjugates
If:
- $\Omega$ is a simply polygonally connected domain
- $u: \Omega \rightarrow \mathbb{R}$ is harmonic
then there exists a harmonic function $v: \Omega \rightarrow \mathbb R$ such that $f = u + iv$ is holomorphic on $\Omega$.

This $v$ that satisfies this is called the **harmonic conjugate** of $u$

To find the **harmonic conjugate** of a function $u$ we use the **CR** equations and integrate partially as in the example bellow:

Find the **harmonic conjugate** of $u(x,y) = x^3 - 3xy^2$.
$$
\begin{align}
 \frac{\partial v}{\partial y} &=\frac{\partial u}{\partial x}  \tag{CR}\\
 \frac{\partial v}{\partial y} &=3x^2 - 3y^2\\
 v &=\int 3x^2 - 3y^2 \partial y \\
 v &=3x^2y - y^3 + C(x) \\
 \frac{\partial v}{\partial x} &=6xy + C'(x) \\
 -\frac{\partial u}{\partial y} &= \frac{\partial v}{\partial x} =6xy + C'(x)\tag{CR} \\
 -(-6xy) &= 6xy + C'(x) \\
 6xy &= 6xy + C'(x) \\
C'(x) &= 0 \\
\implies C(x) &=D \\
\implies v(x,y) &= 3x^2y - y^3 + D \\
\end{align}
$$
### Uniqueness of harmonic conjugates
On top of there always being a harmonic conjugate to a harmonic function, this function is unique up to a constant term.