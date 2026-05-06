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

## Jacobian matrix
The Jacobian matrix of a function $f: \Omega \rightarrow \mathbb R^m$ where $\Omega \subseteq \mathbb R^n$ at a point $x_0 \in \Omega$ is defined as the $m\times n$ matrix:
$$
\begin{align}
(Jf(x_0))_{ij} &= \frac{\partial f_i}{\partial x_j}(x_0) \\
Jf(x_0)&= \begin{pmatrix}
\frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & ... & \frac{\partial f_1}{\partial x_n} \\
\frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & ... & \frac{\partial f_2}{\partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial f_m}{\partial x_1} & \frac{\partial f_m}{\partial x_2} & ... & \frac{\partial f_m}{\partial x_n} \\
\end{pmatrix}
\end{align}
$$
If $f$ is differentiable then:
- It's derivative is unique
- All partial derivatives exist
- $Df(x) = Jf(x)$
## Derivatives of curves
The derivative of a curve $c(t) = (c_1(t), c_2(t), ..., c_n(t))$ is given by
$$
\begin{align}
Jc(t) &= \pmatrix{\frac{\partial c_1}{\partial t} \\ \frac{\partial c_2}{\partial t} \\ \ \ \vdots \\ \frac{\partial c_n}{\partial t}} \\
c'(t) &= \pmatrix{\frac{d c_1}{d t} \\ \frac{d c_2}{d t} \\ \ \ \vdots \\ \frac{d c_n}{d t}}
\end{align}
$$
This can be interpreted as the tangent vector at different points along the curve

For curves $c_1(t), c_2(t)$, a function $f(t): I \rightarrow \mathbb R$ and a $\lambda \in \mathbb R$ we have:
- $(c_1 + c_2)'(t) = c_1'(t) + c_2'(t)$
- $(\lambda c_1)'(t) = \lambda c_1'(t)$
- $(fc_1)'(t) = f'(t)c_1(t) + f(t)c_1'(t)$
- $(c_1 \cdot c_2)'(t) = c_1'(t) \cdot c_2(t) + c_1(t) \cdot c_2'(t)$
- If the output dimension of $c_1, c_2$ is 3 then:
	- $(c_1 \times c_2)'(t) = c_1'(t) \times c_2(t) + c_1(t) \times c_2'(t)$
- $(c_1 \circ f)'(t) = f'(t)c_1'(f(t))$
## Generalized chain rule
If we have the subsets $\Omega \subseteq \mathbb R^n, \Omega' \subseteq \mathbb R^m$ and the functions $f: \Omega \rightarrow \Omega', g: \Omega' \rightarrow \mathbb R^j$.
Then if $f$ is differentiable at $x_0$ and $g$ is differentiable at $f(x_0)$ then:
$$
\begin{align}
D(g\circ f)(x_0) = Df(x_0)Dg(f(x_0))
\end{align}
$$
## Partial derivative existence $\implies$ continuous?
Generally no however, If we strengthen our conditions then our function $f$ is continuous if we have continuous $\frac{\partial f_i}{\partial f_j}$ on an open set around our point.
