A function $F: \mathbb R^n \rightarrow \mathbb R^n$ is called a vector field and can be interpreted as for every point in space our function gives back another vector.

These **vector fields** describe many things in nature like the force of gravity, the velocity of fluids ect.
## Divergence and curl
We can write $\nabla$ as:
$$
\begin{align}
\nabla &= \pmatrix{\frac{\partial}{\partial x} \\ \frac{\partial}{\partial y} \\ \frac{\partial}{\partial z}}
\end{align}
$$
then accepting the **Lovely** notation we can write $\nabla \cdot F$ as:
$$
\begin{align}
\nabla \cdot F &= \frac{\partial F_1}{\partial x} + \frac{\partial F_2}{\partial y} + \frac{\partial F_3}{\partial z}
\end{align}
$$
and we write $\nabla \times F$ as:
$$
\begin{align}
\nabla \times F &= \pmatrix{
\ \ \hat \imath & \ \ \hat \jmath & \ \ \hat k \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
\ F_1 & \ F_2 & \ F_3
} \\
&= \left(\frac{\partial F_3}{\partial y} - \frac{\partial F_2}{\partial z}, \frac{\partial F_3}{\partial x} - \frac{\partial F_1}{\partial z}, \frac{\partial F_2}{\partial x} - \frac{\partial F_1}{\partial y}\right)
\end{align}
$$
These two objects are called the **divergence** and **curl** of $F$ respectively

Additionally, in 2d the curl is defined as $\left(\frac{\partial F_2}{\partial x} - \frac{\partial F_1}{\partial y}\right)$ 

**Divergence** is a measure of how much the field is "diverging" on the specific point which can be seen below:
- Positive divergence:
![[Pasted image 20260415184027.png]]
- Zero divergence:
![[Pasted image 20260415184109.png]]
- Negative divergence:
![[Pasted image 20260415184136.png]]

The **Curl** on the other hand measures how much a vector field "curls" around a specific point and in what axis like so:
![[Pasted image 20260415184525.png]]
A vector field satisfying $\nabla \times F = 0$  is called **irotational**
### Product rules
Let $\phi$ be a scalar function and $F$ be a vector field. Then:
- If $\phi$ has continuous second derivatives then $\nabla \times (\nabla \phi) = 0$
- If $F$ has continuous second partial derivatives then $\nabla \cdot (\nabla \times F) = 0$
- $\nabla \cdot (\phi F) = (\nabla \phi) \cdot F + \phi (\nabla \cdot F)$
- $\nabla \times (\phi F) = (\nabla \phi) \times F + \phi (\nabla \times F)$
## Conservative fields
Conservative fields are functions $F$ where there exists some scalar function $\phi$ such that
$$
\begin{align}
\nabla \phi &= F
\end{align}
$$
When this is the case $\phi$ is called the scalar potential of $F$. (ie gravitational potential energy vs gravitational force)

If $F$ has continuous partial derivatives then we get that:
$$
\begin{align}
\frac{\partial F_2}{\partial x} &= \frac{\partial^2 \phi}{\partial x\partial y} \\
&= \frac{\partial^2\phi}{\partial y \partial x} \\
&= \frac{\partial F_1}{\partial y}
\end{align}
$$
This works with all the other combinations of variables thus:
$$
\begin{align}
\frac{\partial F_1}{\partial y} &= \frac{\partial F_2}{\partial x} \\
\frac{\partial F_2}{\partial z} &= \frac{\partial F_3}{\partial y} \\
\frac{\partial F_1}{\partial z} &= \frac{\partial F_3}{\partial x} \\
\end{align}
$$
It then follows that all conservative vector fields are **irotational**. The converse of this statement is also true on simply connected domains.

Often you will be asked if a vector field is conservative. To test this take the **curl** and if $\nabla \times f = \vec 0$ and the domain of $f$ is simply path connected then your sweet. If $\nabla \times f \not = \vec 0$ then $f$ is not conservative. If these fail then you can try to find $\phi$ by solving the system of PDEs:
$$
\begin{align}
\frac{\partial \phi}{\partial x} &= F_x \\
\frac{\partial \phi}{\partial y} &= F_y \\
\frac{\partial \phi}{\partial z} &= F_z \\
\end{align}
$$
As a recap you can simply integrate $F_x$ wrt $x$ treating $y, z$ as constants and then $c$ becomes $c(y, z)$. You can then differentiate your $\psi(x, y, z)$ wrt $y$, find $c(y, z)$ in terms of $c(z)$ then do the same with $z$ to finally find $c(z)$.
## The Laplacian
The **Laplacian** $\Delta$ is defined by $\Delta = \nabla \cdot \nabla$ and so for $f(x, y, z)$ we get:
$$
\begin{align}
\Delta f(x, y, z) &= \nabla \cdot \nabla f \\
&= \nabla \cdot \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z}\right) \\
&= \frac{\partial^2 f}{\partial x^2} + \frac{\partial^2 f}{\partial y^2} + \frac{\partial^2 f}{\partial z^2}
\end{align}
$$
