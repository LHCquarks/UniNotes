## Path integrals
Say we have a multivariable function that we want to integrate over a specific path as bellow. 
![[Pasted image 20260415154006.png]]
To do this we take our integral over the multivariable function $F(x, y)$ and substitute our parameterized curve $c(t)$ as so:
$$
\begin{align}
\int_c F(x, y) ds &= \int_a^b F(c(t)) |J_c(t)|dt \\
 &= \int_a^b F(c(t)) |c'(t)|dt \\
\end{align}
$$
Here $ds$ represents an infinitesimal displacement vector along the curve.

If we expand our $c(t)$ in terms of it's unit vectors to get $c(t) = x(t) \hat \imath  + y(t) \hat \jmath$ then we can write our equation as:
$$
\begin{align}
\int_c F(x, y) ds &= \int_a^b F(c(t)) |c'(t)|dt \\
&= \int_a^b F(x(t), y(t)) |(x'(t), y'(t))|dt \\
&= \int_a^b F(x(t), y(t)) \sqrt{(x'(t))^2 + (y'(t))^2}dt \\
&= \int_a^b F(x(t), y(t)) \sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2}dt \\
\end{align}
$$
If we were doing this in 3d then we would get the formula:
$$
\begin{align}
\int_c F(x, y, z) ds &= \int_a^b F(x(t), y(t), z(t)) \sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2 + \left(\frac{dz}{dt}\right)^2} dt
\end{align}
$$
## Surface integrals
Surface integrals are similar to path integrals except we integrate over a surface instead of a path.
To do this we introduce a second parameter so that for our function $F(x, y, z)$ we have our surface $S(u, v) = (x(u, v), y(u, v), z(u, v))$. We write the surface integral like so:
$$
\begin{align}
I = \int_S F(x, y, z) dA
\end{align}
$$
where $dA$ represents the size of our small patch of area.
Through our Jacobian:
$$
\begin{align}
I = \iint_S F(S(u, v))|J_S| dudv
\end{align}
$$
This is all well and good but we have another form of $dA$ where it is the magnitude of a normal vector of our surface $d\vec{A}$. This vector $d\vec{A}$ can be expressed as the cross product of the tangent vectors $d\vec u$ and $d \vec v$ where the tangent vector $d\vec w$ is given by
$$
\begin{align}
d\vec w &= \pmatrix{\frac{\partial x}{\partial w}\\ \frac{\partial y}{\partial w}\\ \frac{\partial z}{\partial w}} dw
\end{align}
$$
Therefore we get the formula:
$$
\begin{align}
d\vec A &= \pmatrix{\frac{\partial x}{\partial u} \\ \frac{\partial y}{\partial u} \\ \frac{\partial z}{\partial u}} du \times \pmatrix{\frac{\partial x}{\partial v} \\ \frac{\partial y}{\partial v} \\ \frac{\partial z}{\partial v}} dv \\
&= \pmatrix{\frac{\partial x}{\partial u} \\ \frac{\partial y}{\partial u} \\ \frac{\partial z}{\partial u}} \times \pmatrix{\frac{\partial x}{\partial v} \\ \frac{\partial y}{\partial v} \\ \frac{\partial z}{\partial v}} dudv \\
\end{align}
$$
and finally:
$$
\begin{align}
dA &= \left|d\vec A\right| \\
&= \left|\pmatrix{\frac{\partial x}{\partial u} \\ \frac{\partial y}{\partial u} \\ \frac{\partial z}{\partial u}} \times \pmatrix{\frac{\partial x}{\partial v} \\ \frac{\partial y}{\partial v} \\ \frac{\partial z}{\partial v}}
\right| dudv
\end{align}
$$
If you wish we can then write this out to be:
$$
\begin{align}
I &= \int_S F(x, y, z) dA \\
&= \int_S F(S(u, v))
\begin{Vmatrix}
\hat \imath & \hat \jmath & \hat k \\
\frac{\partial x}{\partial u} & \frac{\partial y}{\partial u} & \frac{\partial z}{\partial u} \\
\frac{\partial x}{\partial v} & \frac{\partial y}{\partial v} & \frac{\partial z}{\partial v} \\
\end{Vmatrix} dudv \\
&= \int_S F(S(u, v)) \sqrt{\left(\frac{\partial y}{\partial u} \frac{\partial z}{\partial v} - \frac{\partial z}{\partial u} \frac{\partial y}{\partial v}\right)^2 + \left(\frac{\partial x}{\partial u} \frac{\partial z}{\partial v} - \frac{\partial z}{\partial u} \frac{\partial x}{\partial v}\right)^2 + \left(\frac{\partial x}{\partial u} \frac{\partial y}{\partial v} - \frac{\partial y}{\partial u} \frac{\partial x}{\partial v}\right)^2}
dudv \\
\end{align}
$$
