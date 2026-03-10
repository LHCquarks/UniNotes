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
For implicit surfaces of the form $S = \{x\in \mathbb R^n: \phi(x) = c\}$ we get that $\nabla \phi(x_0)$ is the normal to our surface at the point $x_0 \in S$ and thus our tangent plane is given by:
$$
\begin{align}
T_{\phi,x_0}  = \{x \in \mathbb R^n: \nabla \phi(x_0) \cdot (x - x_0) = 0\}
\end{align}
$$
We can also write our tangent plane to our function $f$ parametrically as:
$$
\begin{align}
T_{f, x_0} = \left\{x = x_0 + \lambda_1
\begin{pmatrix}
1 \\ 0 \\ \vdots \\ 0 \\ \frac{\partial f}{\partial x_1}
\end{pmatrix} + \lambda_2
\begin{pmatrix}
0 \\ 1 \\ \vdots \\ 0 \\ \frac{\partial f}{\partial x_2}
\end{pmatrix} + \dots + \lambda_n 
\begin{pmatrix}
0 \\ 0 \\ \vdots \\ 1 \\ \frac{\partial f}{\partial x_n}
\end{pmatrix}
\right\}
\end{align}
$$
Further, a tangent line to a surface $f$ in the direction $\hat v$ can be expressed parametrically as:
$$
\begin{align}
L_{f, x_0} = \left\{x = x_0 + \lambda 
\begin{pmatrix} 
v_1 \\ v_2 \\ \vdots \\ v_n \\ \frac{\partial f}{\partial v}(x_0)
\end{pmatrix}
\right\}
\end{align}
$$
