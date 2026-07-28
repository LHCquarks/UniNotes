The current at a point is defined as how much charge passes through a point in one second which can be written $I = \frac{dq}{dt}$. 

We can also define the vector version of current by specifying what direction the current flows in and thus $\vec I = \lambda \vec v$ 
## Surface current density
Say that we had some current flowing over a 2d surface. Then by using the same procedure as above we can find an object called the surface current density given by:
$$
\begin{align}
\vec K = \sigma \vec v
\end{align}
$$
Considering a strip of length $dl_\perp$ we can recover the current with $\vec I = \int \vec K dl_\perp$.

![[Pasted image 20260728131203.png]]
This can also be rewritten as $\frac{d\vec I}{dl_\perp} = \vec K$
## Volume current density
In the exact same way that we extended current to 2d we can extend it to 3d with the volume current density $\vec J$:
$$
\begin{align}
\vec I &= \int \vec J da_\perp \\
\frac{d\vec I}{da_\perp} &= \vec J \\
\vec J &= \rho \vec v
\end{align}
$$
## The continuity equation
By the law of conservation of charge we know that for $\rho$ to decrease there must be an outgoing flux of current. By this we get the equation
$$
\begin{align}
\oint_{\partial S} \vec J \cdot d\vec A &= -\frac{d}{dt}\int_S \rho d \tau \\
\int_S \nabla \cdot \vec J d\tau &= \int_S -\frac{d\rho}{dt} d\tau \\
\nabla \cdot \vec J &= -\frac{d\rho}{dt}
\end{align}
$$
For steady current we know that $\nabla \cdot \vec J = 0$ and so $\frac{d\rho}{dt} = 0$.

This law is effectively a "fifth" Maxwell equation.

## Ampere's Law

