Similarly to the electric field we can define a sort of **potential** to the magnetic field called $A$. However, unlike the electric potential the magnetic potential can not be a scalar as $\nabla \times \vec B = \mu_0 \vec J \not = 0$ and thus we need $A$ to be a vector. For this reason we call $\vec A$ the **vector potential**.

The only other first order differential operation that could produce the magnetic field is thus 
$$
\begin{align}
\vec B = \nabla \times \vec A
\end{align}
$$
which is how we define the vector potential.

## Coulomb Gauge
Just like the electric potential (which we will now call the **scalar potential**) the vector potential has a degree of freedom as adding the grad of a scalar function $g$ produces the same magnetic field:
$$
\begin{align}
\vec B &= \nabla \times \vec A \\
&= \nabla \times \left(\vec A + \nabla g\right)
\end{align}
$$
This degree of freedom is known as a **gauge** something that is discussed in later notes. For now we will work in whats called the **Coulomb gauge**  where we select $g$ in such a way that $\nabla \cdot \vec A = 0$ which will allow us to create some very useful formulas.

## Finding the Vector Potential
The vector potential is often quite hard to find but once acquired becomes really useful in field theories and higher level physics.

One way to find it is through the Ampere-Maxwell equation
$$
\begin{align}
\nabla \times \vec B &= \mu_0 \vec J + \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t} \\
\nabla \times \left(\nabla\times \vec A\right) &= \mu_0 \vec J + \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t} \\
\nabla \left(\nabla \cdot \vec A\right) - \nabla^2 \vec A &= \mu_0 \vec J + \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t} \\
\nabla \left(0\right) - \nabla^2 \vec A &= \mu_0 \vec J + \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t} \\
\nabla^2 \vec A &= -\mu_0 \vec J - \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t} \\
\end{align}
$$
For a constant Electric field this then simplifies to
$$
\begin{align}
\nabla^2\vec A = -\mu_0\vec J
\end{align}
$$
Further, given a constant current that dissipates at infinity we can solve for $\vec A$ in the **coulomb gauge** with the Biot-Sevart law:
$$
\begin{align}
\vec A(\vec r) &= \frac{\mu_0}{4\pi} \int \frac{\vec J(\vec r')}{\mathscr r}d\tau'
\end{align}
$$
and similarly for line and surface currents:
$$
\begin{align}
\vec A(\vec r) &= \frac{\mu_0}{4\pi} \int \frac{\vec I(\vec r')}{\mathscr r}dl' \\
\vec A(\vec r) &= \frac{\mu_0}{4\pi} \int \frac{\vec K(\vec r')}{\mathscr r}dA' \\
\end{align}
$$


