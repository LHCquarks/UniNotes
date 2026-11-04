## Getting the wave equations
Start with the definition of potentials (1), (2), add in the lorentz gauge (3).
$$
\begin{align}
\vec B &= \nabla \times \vec A \tag{1} \\
\vec E &= -\nabla \varphi - \frac{\partial \vec A}{\partial t} \tag{2} \\
0 &= \nabla \cdot \vec A + \frac{1}{c^2} \frac{\partial \varphi}{\partial t} \tag{3}
\end{align}
$$
We can then substitute these into Maxwell's equations to get:
$$
\begin{align}
\nabla \cdot \vec E &= \frac{\rho}{\epsilon_0} \\
\nabla \cdot \left[-\nabla \varphi - \frac{\partial \vec A}{\partial t}\right] &= \frac{\rho}{\epsilon_0} \\
\nabla^2\varphi + \frac{\partial}{\partial t}\left(\nabla \cdot \vec A\right) &= -\frac{\rho}{\epsilon_0} \\
\nabla^2\varphi + \frac{\partial}{\partial t}\left(-\frac{1}{c^2}\frac{\partial \varphi}{\partial t}\right) &= -\frac{\rho}{\epsilon_0} \\
\nabla^2\varphi - \frac{1}{c^2} \frac{\partial^2\varphi}{\partial t^2} &= -\frac{\rho}{\epsilon_0} \\
\Box_w \varphi &= -\frac{\rho}{\epsilon_0} \\
\nabla \times \vec B &= \mu_0\vec J + \mu_0\epsilon_0\frac{\partial \vec E}{\partial t}  \\
\nabla \times \left[\nabla \times \vec A \right] &= \mu_0\vec J + \mu_0\epsilon_0\frac{\partial}{\partial t}\left(-\nabla \varphi - \frac{\partial A}{\partial t}\right)  \\
\nabla (\nabla \cdot \vec A) - \nabla^2 \vec A &= \mu_0\vec J - \mu_0\epsilon_0\nabla\frac{\partial \varphi}{\partial t} - \mu_0\epsilon_0 \frac{\partial^2 A}{\partial t^2}  \\
 - \nabla^2 \vec A + \mu_0\epsilon_0 \frac{\partial^2 A}{\partial t^2} &= \mu_0\vec J - \mu_0\epsilon_0\nabla(-c^2\nabla \cdot \vec A) - \nabla (\nabla \cdot \vec A)   \\
 \nabla^2 \vec A - \frac{1}{c^2}\frac{\partial^2 A}{\partial t^2} &= -\mu_0\vec J - \nabla(\nabla \cdot \vec A) + \nabla (\nabla \cdot \vec A)   \\
 \nabla^2 \vec A - \frac{1}{c^2}\frac{\partial^2 A}{\partial t^2} &= -\mu_0\vec J \\
 \Box_w \vec A&= -\mu_0\vec J \\
\end{align}
$$
This means that in arbitrary charge and current distributions our potentials satisfy the wave equations, how exciting!
## Using Green's function
Now that we have this we will use the Green's function we found for the d'Alembert operator to setup an integral for our solutions. For the scalar potential this is easy as from the properties of Green's functions we have:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{\epsilon_0}\int_{\mathbb R^3} \int_{-\infty}^\infty \rho(\vec r', t') G_\Box(\vec r, t; \vec r', t') dt' d^3 r' \\
&= \frac{1}{\epsilon_0}\int_{\mathbb R^3} \int_{-\infty}^\infty \rho(\vec r', t') \frac{1}{4\pi |\vec r - \vec r'|}\delta(t - t' - |\vec r - \vec r'| / c) dt' d^3 r' \\
&= \frac{1}{\epsilon_0}\int_{\mathbb R^3} \rho(\vec r', t - |\vec r - \vec r'| / c) \frac{1}{4\pi |\vec r - \vec r'|} d^3 r' \\
\end{align}
$$
or if we write $|\vec r - \vec r'| = R$ and $t_r = t - R/c$ this simplifies to
$$
\begin{align}
\varphi(\vec r, t)&= \frac{1}{4\pi \epsilon_0}\int_{\mathbb R^3} \frac{\rho(\vec r', t_r)}{R} d^3 r' \\
\end{align}
$$
For the vector potential case we realize that $\Box_w$ operates on each component separately and thus we just have a scalar wave equation for each. This leads us to getting the integral
$$
\begin{align}
\vec A(\vec r, t) &= \frac{\mu_0}{4\pi} \int \frac{\vec J(\vec r', t_r)}{R} d^3 r'
\end{align}
$$
