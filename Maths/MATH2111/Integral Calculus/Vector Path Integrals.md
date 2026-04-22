## Definition
We can integrate a vector field over a path by dotting the field with our displacement segment $d\vec s$. This type of integral represents how much you are moving with the vector field. In physics we use this to measure the work done against a field.
![[Pasted image 20260422085916.png]]
$$
\begin{align}
I &= \int_C F(x, y, z)d\vec s \\
&= \int_C F(c(t))\cdot \frac{c'(t)}{||c'(t)||}||c'(t)||dt \\
&= \int_C F(c(t))\cdot c'(t)dt \\
\end{align}
$$
An alternate notation for this integral uses the representation of $d\vec s$ as $\pmatrix{dx \\ dy \\ dz}$ thus our integral becomes:
$$
\begin{align}
\int_C F_x dx + F_y dy + F_z dz
\end{align}
$$
## Properties
For a peicewise smooth oriented curve $C$ and the vector fields $F$ and $G$:
$$
\begin{align}
\int_C F \cdot d\vec s + \int_C G\cdot d\vec s &= \int_C (F + C) \cdot d\vec s \\
\int_C \lambda F \cdot d\vec s &= \lambda\int_C F\cdot d\vec s \\
\int_{-C} F\cdot d\vec s &= -\int_C F\cdot d\vec s \\
\int_C F\cdot d\vec s &= \int_{C_1} F \cdot d \vec s + \int_{C_2} F\cdot d\vec s
\end{align}
$$
## Fundamental theorem of vector path integrals
If $F = \nabla \phi$ on some open set $D$ then for every oriented curve $C$ in $D$ with an initial point $p$ and final point $q$ we get
$$
\begin{align}
\int_C F\cdot d\vec s &= \phi(q) - \phi(p)
\end{align}
$$
This also mean that if $C$ is a loop then:
$$
\begin{align}
\oint_C F\cdot d \vec s &= 0
\end{align}
$$
## Green's theorem
Let $\Omega$ be a bounded region who's boundary is $C$. Also let $C$ be peicewise, smooth and simple.
Let $F$ be a continuously differentiable vector field on $\Omega$. Then:
$$
\begin{align}
\iint_\Omega (\nabla \times F) d\vec A &= \oint_C F \cdot d\vec s \\
\end{align}
$$
As a colliery to Green's theorem (Letting $G = \left(-F_2, F_1\right)$) we get the normal form of Green's theorem:
$$
\begin{align}
\iint_\Omega \nabla \cdot G dA &= \oint_C F \cdot \hat n ds
\end{align}
$$
Note that Green's theorem is for specifically the 2d case and thus $\nabla \times F = \frac{\partial F_2}{\partial x} - \frac{\partial F_1}{\partial y}$ 
### Using Greens theorem to find areas
If we select a vector field so that $|\nabla \times F| = 1$ in the direction of $d\vec A$ on the left hand side we have the area of $\Omega$. Using Green's theorem we can then transform this into an integral along the boundary of $\Omega$. An example is below:

Calculate the area bounded by the astroid
$$
\begin{align}
(x^2)^{1/3} + (y^2)^{1/3} &= a^{2/3} \\
\end{align}
$$
where $a > 0$.

This is a flat surface so we simply need
$$
\begin{align}
\frac{\partial F_2}{\partial x} - \frac{\partial F_1}{\partial y} &= 1.\\
\end{align}
$$
A simple function that solves this is $F(x, y) = \braket{0, x}$. Thus setting up the integral we have:
$$
\begin{align}
\iint_\Omega (\nabla \times \braket{0, x}) d\vec A &= \oint_C \braket{0, x}\cdot d\vec s
\end{align}
$$
Next we find a parametric equation for $C$. Moving $y$ to the left hand side we can solve for x:
$$
\begin{align}
(x^2)^{1/3} &=  a^{2/3} - (y^2)^{1/3}  \\
x^2 &=  \left(a^{2/3} - (y^2)^{1/3}\right)^3  \\
x &=  \pm\left(a^{2/3} - (y^2)^{1/3}\right)^{3/2}  \\
\end{align}
$$
Letting $y = t$ we get the two curves:
$$
\begin{align}
c_1(t) &= \braket{-\left(a^{2/3} - (t + a)^{2/3}\right)^{3/2}, t} & t \in [-a, 0]\\
c_2(t) &= \braket{\left(a^{2/3} - t^{2/3}\right)^{3/2}, t} & t \in [0, a]\\ 
\end{align}
$$
thus we have that
$$
\begin{align}
A &= \int_{-a}^0 \braket{0, t} \cdot c_1'(t) dt +\int_{0}^a \braket{0, t} \cdot c_2'(t) dt \\
&= \int_{-a}^0 t dt +\int_{0}^a  t dt \\
\end{align}
$$
