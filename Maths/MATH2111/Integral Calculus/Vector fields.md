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

**Divergence** is a measure of how much the field is "diverging" on the specific point which can be seen below:
