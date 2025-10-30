## Path integrals
### curves in $\mathbb R^2$
Looking in $\mathbb R^2$ we can define the parametric curve $\gamma(t) = (\gamma_1(t), \gamma_2(t)) : t \in [a, b]$ where $\gamma_1$ and $\gamma_2$ are real-valued.

- This curve is continuous if and only if $\gamma_1$ and $\gamma_2$ are continuous
- The initial point of this curve is $\gamma(a)$ and the end is $\gamma(b)$
- The range of the curve is the set of points $\{\gamma(t): t\in [a, b]\}$
- $\gamma$ is said to be
	- closed if $\gamma(a) = \gamma(b)$
	- simple if $\gamma$ never intersects itself except perhaps at the end points
### Joint curves
We are able to join two curves $\alpha:[a,b] \rightarrow \mathbb R^2, \beta:[c,d] \rightarrow \mathbb R^2$ if
- $b = c$
- $\alpha(b) = \beta(c)$
then the joined curve is:
$$
\begin{align}
\alpha \sqcup \beta = \begin{cases} \alpha(t) & a\le t \lt b \\ \beta(t) & c \le t \le d\end{cases}
\end{align}
$$
### Reverse curves
We can instead move through $\gamma$ backwards and this is denoted by $\gamma^*$ and is given by
$$
\begin{align}
\gamma^*: [-b, -a] \rightarrow \mathbb R^2 \\
\gamma^*(t) = \gamma(-t)
\end{align}
$$
### Reparametrisation
Suppose that:
- $\gamma: [a, b] \rightarrow \mathbb R^2$ is a curve, and
- $h$ is a *continuous* *bijection* from $[c, d]$ to $[a, b]$ such that $h(c) = a$ and $h(d)= b$
Then $\gamma \circ h: [c, d] \rightarrow \mathbb R^2$ is also a curve called a reparametrisation of $\gamma$ and has the formula $\gamma(h(t)) = (\gamma_1(h(t)), \gamma_2(h(t)))$ where $t \in [c,d]$.
### Smooth curves
We define the tangent vector $\gamma ' = (\gamma_1 ', \gamma_2 ')$ provided $\gamma_1'$ and $\gamma_2'$ exist.

We say that $\gamma$ is:
- continuously differentiable if the derivative $\gamma'$ exists and is continuous on $[a, b]$
- smooth if it is continuously differentiable *and* $\gamma'(t) \not = 0$  for all $t \in [a,b]$
## Length
A curve $\gamma: [a, b] \rightarrow \mathbb R^2$ is **piecewise smooth** if it is a join of finitely many smooth curves.

The length of a **piecewise smooth** curve is defined by the formula:
$$
\begin{align}
\text{Length}(\gamma) = \int_a^b |\gamma'(t)| dt
\end{align}
$$
Note that where $\gamma'$ is not defined we just take it's value as $0$ as singular points make no difference.
## Orientation
If $\gamma$ is a simple closed curve then taking the complement of the range of gamma gives two disjoint domains:
- The domain that is bounded is refereed to as the **interior** of the curve written as $\text{Int}(\gamma)$
- The domain that is unbounded is the **exterior** of the curve written as $\text{Ext}(\gamma)$

We define the **standard orientation** of the curve $\gamma$ as the direction where the $\text{Int}(\gamma)$ is always on the left of the curve. In normal person terms we go along the curve in an (anti-clockwise direction)
## Line integrals
Let $\Omega$ be an open subset of $\mathbb R^2$, $V: \Omega \rightarrow \mathbb R^2$ be a vector field on $\Omega$ and $\gamma: [a,b] \rightarrow \mathbb \Omega$ be a **piecewise smooth** curve. Then we define the line integral:
$$
\begin{align}
\int_\gamma V(\vec{s}) d\vec{s} = \int_a^b V(\gamma(t))\cdot\gamma'(t)dt
\end{align}
$$
### Linearity
Suppose that both $V, W$ are vector fields then we get that:
$$
\begin{align}
\int_\gamma \lambda V(\vec{s}) + \mu W(\vec s) d\vec s = \lambda\int_\gamma V(\vec s) d\vec s + \mu \int_\gamma W(\vec s) d\vec{s}
\end{align}
$$
### Reparametrisation
If $\delta$ is a reparametrisation of $\gamma$ then
$$
\begin{align}
\int_\gamma V(\vec s) d\vec s = \int_\delta V(\vec s) d\vec s
\end{align}
$$
### Joint curves
If $\gamma = \alpha \sqcup \beta$ then
$$
\begin{align}
\int_\gamma V(\vec s) d\vec s = \int_\alpha V(\vec s) d\vec s + \int_\beta V(\vec s) d\vec s
\end{align}
$$
### Orientation
Line integrals depend on the orientation of the parameterized curve 
$$
\begin{align}
\int_{\gamma^*} V(\vec s) d\vec s = - \int_\gamma V(\vec s) d\vec s
\end{align}
$$
### Size
The size of a line integral is limited by the size of the vector field and the length of the parameterized curve. In fact we get that
$$
\begin{align}
\left|\int_\gamma V(\vec s ) d\vec s\right| \le M \text{ Length} (\gamma)
\end{align}
$$
where $M \in \mathbb R$ is such that $|V(\vec s)| \le M$  for all $\vec{s} \in \text{Range}(\gamma)$ 
## Formula
A contour integral is defined by
$$
\begin{align}
\int_\gamma f(z) dz = \int_a^b f(\gamma(t))\gamma'(t)dt
\end{align}
$$
$$
\begin{align}
f(w) = \frac{1}{2\pi} \int_0^{2\pi} f(w+re^{i\theta})d\theta
\end{align}
$$
