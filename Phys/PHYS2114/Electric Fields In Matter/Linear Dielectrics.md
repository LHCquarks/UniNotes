Even given $\vec D$ we can not find $\vec E$ without $\vec P$ and so finding $\vec P$ for various materials will be very helpful. As it turns out it is an extremely good approximation to say that $\vec P$ varies linearly with $\vec E$:
$$
\begin{align}
\vec P &= \epsilon_0 \chi_e \vec E
\end{align}
$$
where $\chi_e$ is the **electric susceptibility** of the material. Materials that obey this are called **linear dielectrics**.

With this we can find a new formula for $\vec D$:
$$
\begin{align}
\vec D &= \epsilon_0 \vec E + \vec P \\
&= \epsilon_0 \vec E + \epsilon_0\chi_e\vec E \\
&= \epsilon_0 (1 + \chi_e)\vec E \\
\end{align}
$$
Thus $\vec D$ is also linearly proportional to $\vec E$ by a factor of $\epsilon_0 (1 + \chi_e)$ something we sometimes rewrite as $\epsilon$ the electric permittivity of the material or $\epsilon_0 \epsilon_r$ where $\epsilon_r$ is the relative permittivity of the material.
## Boundary conditions
In the setting of linear dielectrics we can acquire a new expression for the bound charge volume with:
$$
\begin{align}
\rho_b &= -\nabla \cdot \vec P \\
& = -\nabla \cdot \left(\epsilon_0 \frac{\chi_e}{\epsilon}\vec D\right) \\
&= -\left(\frac{\chi_e}{1 + \chi_e}\right)\rho_f
\end{align}
$$
Thus in a linear dielectric, as long as $\rho_f = 0$  there is no bound volume charge and thus all the bound charge lives on the boundary of the material.

As long as this is the case then Laplace's equation holds. Further we get the continuity equation
$$
\begin{align}
\epsilon_{\text{above}}\vec E_{\text{above}} - 
\epsilon_{\text{below}}\vec E_{\text{below}} &= \sigma_f
\end{align}
$$
## Energy in a capacitor
Suppose we have a capacitor that has a dielectric between the two plates. The capacitance of the dielectric filled capacitor is given by $C = \epsilon_r C_{\text{vac}}$.

This would indicate that the work done to charge a capacitor is the same as with a normal capacitor but off by a factor of $\epsilon_r$. This is true! Our total work equation becomes
$$
\begin{align}
W &= \frac{1}{2}\int \epsilon_r E^2 d\tau \\
&= \frac{1}{2}\int \vec D \cdot \vec E d\tau
\end{align}
$$
