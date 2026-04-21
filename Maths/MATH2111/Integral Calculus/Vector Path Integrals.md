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
