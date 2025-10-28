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
We can instead move through $\gamma$ backwards and this is denoted by $\gamma^*$

### Reperamiterisation
We can compos $\gamma$ with $h$, written as $\gamma \circ h$, by defining a new interval $[c, d]$ if $h(c) = a$ and $h(d) = b$ and $h(x)$ is bijective.

### Smooth curves
We define $\gamma ' = (\gamma_1 ', \gamma_2 ')$. 

If $\gamma (t)$ is continuously differentiable and $\gamma ' (t) \not = 0$ then we call the curve **smooth**


## Formula
A contour integral is defined by
$$
\begin{align}
\int_\gamma f(z) dz = \int_a^b f(\gamma(t))\gamma'(t)dt
\end{align}
$$
