## A reminder of the inverse function thrm from 2d
Take a function $y = f(x)$ then if $f$ is continuously differentiable around $x = a$ and $f'(a) \not = 0$ then there exists a local function $g(x)$ such that $g(x) = f^{-1}(x)$ on some region around $a$.

## The inverse function thrm
This is a generalization of the inverse function thrm from 2d and as such we will just replace the lower dimensional objects above with their higher dimensional counterparts.

Suppose that $F: \mathbb R^n \rightarrow \mathbb R^n$ is in $C^1$, and $J_F(a)$ is invertable ($\det (J_F(a)) \not = 0$) then there exists open neighborhoods $U$ and $V$ such that $F: U \rightarrow V$ is invertable (call said inverse $G$) and $J_G(F(a))$ exists and is $J_F(a)^{-1}$.

From here you can use the value of the Jacobian to find a best affine approximation for $G$.
## The Implicit function thrm
Suppose there is a function $\phi: \mathbb R^{m + 1} \rightarrow \mathbb R$ and let the point $(x_1, x_2, \dots, x_m, z)$ be written as $(\vec x, z)$. Let $(\vec a, b)$ satisfy $\phi(\vec a, b) = 0$. If $\frac{\partial \phi}{\partial z} \not = 0$ then there exists open sets $U \in \mathbb R^m$ and $V \in \mathbb R$ and a subjective function $F: U \rightarrow V$ which is $C^1$ such that for all $\vec a \in U$, $b \in V$ we have that $\phi(\vec a, F(\vec a))$. 

In other words, as long as $\frac{\partial \phi}{\partial z} \not =0$   then there exists a local $C^1$ function who's image is equal to the surface $\phi(\vec x, z) = 0$ on said local region.