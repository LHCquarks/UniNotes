## Change of variables
Given an integral what is our higher dimensional equivalent to the $u$ sub?

Say we have a region $u, v$ and we have some map $\vec r(u, v)$ that takes us from our $u, v$ world to our $x, y$ world. Then we can consider the image of a small rectangular region in $u, v$ like so:
![[Pasted image 20260415103238.png]]
Now, The area of our square originally was $dudv$ and thus the area in the $x,y$ space is $|\det(J)|dudv$. This means we get that:
$$
\begin{align}
dxdy = |\det(J)|dudv
\end{align}
$$
Thus our change of variable formula in the multivariable case is:
$$
\begin{align}
\iint_{F(A)} f(x, y) dxdy &= \iint_{A} f(F(u, v)) |\det(J)| dudv
\end{align}
$$
This also generalizes to any dimension with the bellow formula
$$
\begin{align}
\int_{F(A)} f(\vec y) d\vec y &= \int_A (f \circ F)(\vec x) |\det(J_F(\vec x))| d\vec x
\end{align}
$$
## Common substitutions
Some common substitutions include:
### Polar sub
$$
\begin{align}
x &= r\cos(\theta) \\
y &= r\sin(\theta)
\end{align}
$$
for $r > 0, \theta \in [0, 2\pi]$.
We get 
$$
\begin{align}
|\det(J)| &= 
\begin{Vmatrix}
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta} \\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta} \\
\end{Vmatrix} \\
&= 
\begin{Vmatrix}
\cos\theta & -r\sin\theta \\
\sin\theta & r\cos\theta \\
\end{Vmatrix} \\
&= |r\cos^2\theta + r \sin^2\theta| \\
&= r
\end{align}
$$
### Cylindrical coordinates
$$
\begin{align}
x &= r\cos\theta\\
y &= r\sin\theta\\
z &= z\\
\end{align}
$$
for $r > 0, \theta \in [0, 2\pi], z \in \mathbb R$.
We get
$$
\begin{align}
|\det(J)| &= 
\begin{Vmatrix}
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta} & \frac{\partial x}{\partial z}\\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta} & \frac{\partial y}{\partial z}\\
\frac{\partial z}{\partial r} & \frac{\partial z}{\partial \theta} & \frac{\partial z}{\partial z}\\
\end{Vmatrix} \\
&= 
\begin{Vmatrix}
\cos\theta & -r\sin\theta & 0\\
\sin\theta & r\cos\theta  & 0\\
0 & 0 & 1\\
\end{Vmatrix} \\
&= |r\cos^2\theta + r \sin^2\theta| \\
&= r
\end{align}
$$
### Spherical coordinates
$$
\begin{align}
x &= \rho \cos\theta \sin\phi \\
y &= \rho \sin\theta \sin\phi \\
z &= \rho \cos\phi \\
\end{align}
$$
for $\rho > 0, \theta \in [0, 2\pi], \phi \in [0, \frac{\pi}{2}]$. In these coordinates:
- $\rho$ is the distance from the origin
- $\theta$ is the angle from the positive x-axis in the x-y plane
- $\phi$ is the angle from the positive z-axis

We get:
$$
\begin{align}
|\det(J)| &= 
\begin{Vmatrix}
\frac{\partial x}{\partial \rho} & \frac{\partial x}{\partial \theta} & \frac{\partial x}{\partial \phi}\\
\frac{\partial y}{\partial \rho} & \frac{\partial y}{\partial \theta} & \frac{\partial y}{\partial \phi}\\
\frac{\partial z}{\partial \rho} & \frac{\partial z}{\partial \theta} & \frac{\partial z}{\partial \phi}\\
\end{Vmatrix} \\
&= 
\begin{Vmatrix}
\cos\theta \sin\phi & -\rho\sin\theta\sin\phi & \rho\cos\theta\cos\phi\\
\sin\theta\sin\phi & \rho\cos\theta\sin\phi  & \rho\sin\theta\cos\phi\\
\cos\phi & 0 & -\rho\sin\phi\\
\end{Vmatrix} \\
&= |\cos\theta\sin\phi[\rho\cos\theta\sin\phi \cdot (-\rho\sin\phi) - \rho\sin\theta\cos\phi \cdot 0]\\
&\ \ \ \ \ \  + \rho\sin\theta\sin\phi[\sin\theta\sin\phi \cdot(-\rho\sin\phi) - \rho\sin\theta\cos\phi \cdot\cos\phi] \\
&\ \ \ \ \ \ +\rho\cos\theta\cos\phi[\sin\theta\sin\phi\cdot0 - \rho\cos\theta\sin\phi\cdot\cos\phi]| \\
&=|-\rho^2\cos^2\theta \sin^3\phi\\
&\ \ \ \ \ \  - \rho^2\sin^2\theta\sin^3\phi - \rho^2 \sin^2\theta\sin^2\phi \cos\phi \\
&\ \ \ \ \ \ - \rho^2\cos^2\theta \sin\phi \cos^2\phi| \\
&=|\rho^2\sin^3\phi + \rho^2 \sin\phi\cos^2\phi | \\
&=\rho^2|\sin\phi| \\
\end{align}
$$
because $\phi \in [0, \frac{\pi}{2}]$ we know $\sin\phi \ge 0$ thus we can drop the absolute values and get:
$$
\begin{align}
|\det(J)| = \rho^2\sin\phi
\end{align}
$$
## Inverse substitution
Say instead of a substitution of the form
$$
\begin{align}
(x, y) = F(u, v)
\end{align}
$$
we want a substitution of the form
$$
\begin{align}
(u, v) = F(x, y).
\end{align}
$$
This is the same as the last but instead of $F$ we have $F^{-1}$. The formula for this substitution is thus:
$$
\begin{align}
\iint_{A} f(x, y) dxdy &= \iint_{F(A)} f(x, y) |\det(J_{F^{-1}})| dudv \\
&= \iint_{F(A)} f(x, y) \frac{1}{|\det(J_{F})|} dudv.
\end{align}
$$