## Definition
The flux of a vector field across a surface is the amount of the vector field "flowing across" the surface of an object per unit area. This integral is written like so
$$
\begin{align}
I &= \iint_S F\cdot d \vec A \\
\end{align}
$$
In this equation the area vector $d\vec A$ has a magnitude of $dA$ and is in the direction of the normal to the surface thus:
$$
\begin{align}
I &= \iint_S F\cdot d\vec A \\
&= \iint_S F\cdot \hat n dA
\end{align}
$$
We can also ignore the $\hat n$ part and just notice that $d\vec A = d\vec u \times d\vec v$ and thus:
$$
\begin{align}
d\vec A &= \pmatrix{\frac{\partial x}{\partial u} \\ \frac{\partial y}{\partial u} \\ \frac{\partial z}{\partial u}} \times \pmatrix{\frac{\partial x}{\partial v} \\ \frac{\partial y}{\partial v} \\ \frac{\partial z}{\partial v}}
\end{align}
$$
## Boundaries of surfaces
For a surface $S$ we write it's boundary as $\partial S$. The orientation of the boundary curve is such that when running along the curve the surface is always on your left.
## Stoke's theorem
Stoke's theorem is a generalization of Green's theorem and thus has basically the same form except this time it works in 3d.
$$
\begin{align}
\iint_S (\nabla \times F)\cdot d\vec A &= \oint_{\partial S} F \cdot d\vec s
\end{align}
$$
WOW!

Note that for conservative $F$ we get that both integrals are $0$

## Gauss' Divergence theorem
Let $V$ be a bounded solid simple region in 3-d space. Let $F$ be a vector field that is continuously differentiable on $T$. Then:
$$
\begin{align}
\iint_{\partial S} F \cdot d\vec A &= \iiint_V \nabla \cdot F dV
\end{align}
$$
## Alternate definitions of divergence and curl
If we define the divergence of a vector field $F$ as:
$$
\begin{align}
\nabla \cdot F &= \lim_{V\rightarrow 0} \frac{1}{V} \iint_S F \cdot d\vec A
\end{align}
$$
Where:
- S is a surface enclosing a point $p$
- $V$ is the volume of the region contained by the surface $S$
From this definition we get original definition of divergence

We can define the divergence of a vector field as:
$$
\begin{align}
\nabla \times F \cdot \hat n&= \lim_{A \rightarrow 0} \frac{1}{A} \int_C F\cdot d\vec s
\end{align}
$$

Where:
- $C$ is a closed loop enclosing a point $p$ 
- $A$ is the area of region enclosed by $C$
- $\hat n$ is a vector perpendicular to the surface $A$