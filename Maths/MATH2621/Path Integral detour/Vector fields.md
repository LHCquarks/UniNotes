Vector fields are functions $V: \mathbb R^n \rightarrow \mathbb R^n$. These map every point in a space to another vector.

We can split any vector field up into multiple real functions as such $V = (u_1, u_2, u_3, ... , u_n)$ 

For 2d vector fields we have the following types:
## Closed vector fields
A vector field $V = (v, w)$ is closed (aka curl-free) iff $\frac{\partial w}{\partial x} = \frac{\partial v}{\partial y}$
## Exact vector fields
A vector field $V = (v, w)$ is exact (aka conservative) iff there exists a function $u: \Omega \rightarrow \mathbb R$ such that $\frac{\partial u}{\partial x} = v$ and $\frac{\partial u}{\partial y} = w$.
This is often written as $V = \nabla u$ 

If $u$ is twice continuously differentiable, then
$$
\begin{align}
\frac{\partial w}{\partial x} = \frac{\partial^2 u}{\partial x \partial y} = \frac{\partial^2 u}{\partial y \partial x} = \frac{\partial v}{\partial y}
\end{align}
$$
Which means that Continuously differentiable exact vector fields are closed

Further we have the theorem that if:
- $\Omega$ is a simply connected domain, and
- $V$ is a closed continuously differentiable vector field in $\Omega$.
Then $V$ is exact.