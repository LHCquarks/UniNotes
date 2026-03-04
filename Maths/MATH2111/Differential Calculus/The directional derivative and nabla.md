## The Directional Derivative
If we have $f: \Omega \subseteq \mathbb R^n \rightarrow \mathbb R, x_0 \in \text{Int}(\Omega)$ and $v \in \mathbb R^n$ be not zero. The directional derivative of $f$ in the direction $v$ is defined by:
$$
\begin{align}
\frac{\partial f}{\partial v}(x_0) = \lim_{h \rightarrow 0} \frac{f(x_0 + h\hat{v}) - f(x_0)}{h}
\end{align}
$$
where $\hat{v} = v / |v|$.
### Better formula
This definition simplifies to:
$$
\begin{align}
\left(\frac{\partial f}{\partial x_1}(x_0), \frac{\partial f}{\partial x_2}(x_0), ...,\frac{\partial f}{\partial x_n}(x_0) \right) \hat{v}
\end{align}
$$
Because this row vector of derivatives are pretty important we write it as $\nabla f$ pronounced **nabla**