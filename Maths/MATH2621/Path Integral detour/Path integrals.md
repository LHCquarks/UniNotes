Path integrals / line integrals are defined as bellow:

Let $\Omega$ be an open subset of $\mathbb R^2$, $V: \Omega \rightarrow \mathbb R^2$ be a vector field on $\Omega$ and $\gamma: [a,b] \rightarrow \mathbb \Omega$ be a **piecewise smooth** curve. Then we define the line integral:
$$
\begin{align}
\int_\gamma V(\vec{s}) d\vec{s} = \int_a^b V(\gamma(t))\cdot\gamma'(t)dt
\end{align}
$$
## Linearity
Suppose that both $V, W$ are vector fields then we get that:
$$
\begin{align}
\int_\gamma \lambda V(\vec{s}) + \mu W(\vec s) d\vec s = \lambda\int_\gamma V(\vec s) d\vec s + \mu \int_\gamma W(\vec s) d\vec{s}
\end{align}
$$
## Reparametrisation
If $\delta$ is a reparametrisation of $\gamma$ then
$$
\begin{align}
\int_\gamma V(\vec s) d\vec s = \int_\delta V(\vec s) d\vec s
\end{align}
$$
Because the parametrisation of our curve does not matter (The only thing that matters is the actual path of the curve) we also call our line integral a **path** integral
## Joint curves
If $\gamma = \alpha \sqcup \beta$ then
$$
\begin{align}
\int_\gamma V(\vec s) d\vec s = \int_\alpha V(\vec s) d\vec s + \int_\beta V(\vec s) d\vec s
\end{align}
$$
## Orientation
Line integrals depend on the orientation of the parameterized curve 
$$
\begin{align}
\int_{\gamma^*} V(\vec s) d\vec s = - \int_\gamma V(\vec s) d\vec s
\end{align}
$$
## Size
The size of a line integral is limited by the size of the vector field and the length of the parameterized curve. In fact we get that
$$
\begin{align}
\left|\int_\gamma V(\vec s ) d\vec s\right| \le M \text{ Length} (\gamma)
\end{align}
$$
where $M \in \mathbb R$ is such that $|V(\vec s)| \le M$  for all $\vec{s} \in \text{Range}(\gamma)$ 