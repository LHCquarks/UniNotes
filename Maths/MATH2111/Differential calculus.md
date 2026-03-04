## Affine approximation
### Affine & linear function
A linear function is one such that $L(\lambda x + y) = \lambda L(x) + L(y)$. All linear maps can also be represented as a matrix so that $L(x) = A_{L}x$

An affine function is a function $T(x)$ such that there exists a linear function $L(x)$ and a point $y_0$ such that $T(x) = L(x) + y_0$
### Approximation
Let $x_0$ be an interior point of $\Omega \subseteq \mathbb R^n$. A function $f: \Omega \rightarrow \mathbb R^m$ has an **affine approximation** at $x_0$ if there exists a linear map $L: \mathbb R^n \rightarrow \mathbb R^m$ such that
$$
\begin{align}
\lim_{x\rightarrow x_0} \frac{|f(x) - f(x_0) - L(x - x_0)|}{|x - x_0|} = 0
\end{align}
$$
If $f$ has an **affine approximation** at a point $x_0$ then we say $f$ is **differentiable** at $x_0$

This is effectively akin to finding a tangent surface ($L(x)$) to your function at the point $x_0$.
### Uniqueness
If such a linear map $L(x)$ exists then it is unique and we call it the derivative of $f$ at $x_0$ and we denote it as:
$$
\begin{align}
Df(x_0) = D_{x_0} f
\end{align}
$$
### Implication of continuity
Just like the single variable case we find that if a function is differentiable at a point $x_0$ then it is also continuous at $x_0$
## Partial derivatives
If $\Omega \subseteq \mathbb R^n$ and $x_0 \in \text{Int}(\Omega)$ and $f: \Omega \rightarrow \mathbb R$, then the partial derivative of $f$ with respect to $x_j$ at $x_0$ is defined as:
$$
\begin{align}
\frac{\partial f}{\partial x_j} &= \lim_{h\rightarrow 0} \frac{f(x_0 + h e_j) - f(x_0)}{h}
\end{align}
$$

## Jacobin matrix
The Jacobin matrix of a function $f: \Omega \rightarrow \mathbb R^m$ where $\Omega \subseteq \mathbb R^n$ at a point $x_0 \in \Omega$ is defined as the $m\times n$ matrix:
$$
\begin{align}
(Jf(x_0))_{ij} &= \frac{\partial f_i}{\partial x_j}(x_0) \\
Jf(x_0)&= \begin{pmatrix}
\frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & ... & \frac{\partial f_1}{\partial x_n} \\
\frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & ... & \frac{\partial f_2}{\partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial f_n}{\partial x_1} & \frac{\partial f_n}{\partial x_2} & ... & \frac{\partial f_n}{\partial x_n} \\
\end{pmatrix}
\end{align}
$$
