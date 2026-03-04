## The Directional Derivative
If we have $f: \Omega \subseteq \mathbb R^n \rightarrow \mathbb R, x_0 \in \text{Int}(\Omega)$ and $v \in \mathbb R^n$ be not zero. The directional derivative of $f$ in the direction $v$ is defined by:
$$
\begin{align}
\frac{\partial f}{\partial v}(x_0) = \lim_{h \rightarrow 0} \frac{f(x_0 + h\hat{v}) - f(x_0)}{h}
\end{align}
$$
where $\hat{v} = v / |v|$.
### Better formula
This definition simplifies when $f$ is differentiable to:
$$
\begin{align}
\frac{\partial f}{\partial v} &= \left(\frac{\partial f}{\partial x_1}(x_0), \frac{\partial f}{\partial x_2}(x_0), ...,\frac{\partial f}{\partial x_n}(x_0) \right) \hat{v} \\
&= 
\begin{pmatrix}
\frac{\partial f}{\partial x_1}(x_0) \\ \frac{\partial f}{\partial x_2}(x_0) \\ \vdots \\ \frac{\partial f}{\partial x_n}(x_0) 
\end{pmatrix}
\cdot \hat{v}
\end{align}
$$
Because this vector of derivatives are pretty important we write it as $\nabla f$ pronounced **nabla**.

We can also change this to
$$
\begin{align}
\frac{\partial f}{\partial v}(x_0) &= \nabla f(x_0) \cdot \hat{v} \\
&= ||\nabla f(x_0) || \cos\theta
\end{align}
$$
where theta is the angle between $\nabla f(x_0)$ and $v$. 
Further this is maximized when $\theta = 0$ hence:
- $\nabla f(x_0)$ points in the direction of steepest accent 
- $-\nabla f(x_0)$ points in the direction of the steepest decent
- $\nabla f(x_0)$ is perpendicular to the level direction
## Tangent planes and lines
When $f: \Omega \rightarrow \mathbb R$ then we get the tangent plane to be 
$$
\begin{align}
T_{x_0}f(x) &= \nabla f(x_0) \cdot (x - x_0) + f(x_0)
\end{align}
$$
For implicit surfaces of the form $\phi(x) = 0$ the 