Take Faraday's law and take the dot product with $\vec B$
$$
\begin{align}
\vec \nabla \times \vec E &= -\frac{\partial \vec B}{\partial t} \\
\vec B \cdot \left[ \vec \nabla \times \vec E\right] &= -\vec B \cdot \frac{\partial \vec B}{\partial t}
\end{align}
$$
Now looking at the RHS closely it is equal to $-\frac{\partial}{\partial t}\left( \frac{B^2}{2}\right)$. This is interesting as it looks like our work formula. 

To make this more explicit we can also multiply both sides by $-\frac{1}{\mu_0}$ to get:
$$
\begin{align}
-\frac{1}{\mu_0}\vec B \cdot \left[\vec \nabla \times \vec E\right] &= \frac{\partial}{\partial t}\left(\frac{B^2}{2\mu_0}\right)
\end{align}
$$
This then inspires us to do the same this with the electric field using the Ampere-Maxwell law. Multiplying by $\vec E / \mu_0$ we get:
$$
\begin{align}
\vec \nabla \times \vec B &= \mu_0 \vec J + \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t} \\
\frac{1}{\mu_0}\vec E \cdot \left[\vec \nabla \times \vec B\right] &= \vec J\cdot \vec E + \epsilon_0 \vec E \cdot \frac{\partial \vec E}{\partial t} \\
&= \vec J\cdot \vec E + \frac{\partial}{\partial t}\left(\frac{\epsilon_0 E^2}{2}\right) \\
\end{align}
$$
We can then add both sides together to get
$$
\begin{align}
\vec J\cdot \vec E + \frac{\partial}{\partial t} \left(\frac{B^2}{2\mu_0} + \frac{\epsilon_0 E^2}{2}\right) &= \frac{1}{\mu_0}\left(\vec E \cdot \left[\vec \nabla \times \vec B\right] - \vec B \cdot \left[\vec \nabla \times \vec E\right]\right) \\
\vec J \cdot \vec E+ \frac{\partial}{\partial t} \left(\frac{B^2}{2\mu_0} + \frac{\epsilon_0 E^2}{2}\right) &= \frac{1}{\mu_0}\left(-\vec \nabla \cdot \left[\vec E \times \vec B\right]\right) \\
\frac{\partial}{\partial t} \left(\frac{B^2}{2\mu_0} + \frac{\epsilon_0 E^2}{2}\right) &= - \vec J\cdot \vec E -\vec \nabla \cdot \left[\frac{1}{\mu_0}\vec E \times \vec B\right] \\
\end{align}
$$
Defining $\vec S = \frac{1}{\mu_0} \left[\vec E \times \vec B\right]$ we get
$$
\begin{align}
\frac{\partial}{\partial t} \left(\frac{B^2}{2\mu_0} + \frac{\epsilon_0 E^2}{2}\right) &= - \vec J\cdot \vec E -\vec \nabla \cdot \vec S \\
\end{align}
$$
Finally, integrating over an arbitrary volume $V$ we get
$$
\begin{align}
\int_V \frac{\partial}{\partial t} \left(\frac{B^2}{2\mu_0} + \frac{\epsilon_0 E^2}{2}\right)d\tau &= -\int_V\vec J \cdot \vec E  d\tau - \int_{\partial V} \vec S \cdot d\vec A
\end{align}
$$
On the left hand side we get the rate of change of the energy stored in the electric and magnetic fields whist on the right hand side $\vec J \cdot \vec E$ is the work done on charges inside the surface by the electric field and thus $\vec S \cdot d\vec A$ is the out-flowing energy.

This implies that $\vec S$ is the energy flux and represents the flow of energy. This is called the Poynting vector