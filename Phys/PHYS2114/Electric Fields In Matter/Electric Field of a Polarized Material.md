A material that has been polarized produces its own electric field in response. This page tries to describe field.
## Bound charges
We know that the voltage from a dipole is given from the dipole term in the multi-pole expansion
$$
\begin{align}
V(\vec r) &= \frac{1}{4\pi\epsilon_0} \frac{\vec p \cdot \hat {\mathscr r}}{\mathscr r^2}
\end{align}
$$
By taking $\vec p = \vec P V$ we get $d\vec p = \vec P d\tau$ and so
$$
\begin{align}
dV(\vec r) &= \frac{1}{4\pi\epsilon_0} \frac{d\vec p \cdot \hat {\mathscr r}}{\mathscr r^2} \\
&= \frac{1}{4\pi\epsilon_0} \frac{\vec P(\vec r') \cdot \hat {\mathscr r}}{\mathscr r^2} d \tau'\\
V &= \frac{1}{4\pi\epsilon_0} \int_{\mathcal V}\frac{\vec P(\vec r') \cdot \hat {\mathscr r}}{\mathscr r^2} d \tau'\\
 &= \frac{1}{4\pi\epsilon_0} \int_{\mathcal V} \vec P(\vec r')\cdot \nabla'\left(\frac{1}{\mathscr r}\right) d \tau'\\
\end{align}
$$
Using integration by parts we then get
$$
\begin{align}
V &= \frac{1}{4\pi\epsilon_0} 
\left[
\int_\mathcal V \nabla'\cdot \left(\frac{\vec P}{\mathscr r}\right) d \tau' -
\int_\mathcal V \frac{1}{\mathscr r}\nabla'\cdot \vec P d \tau'
\right]\\
&= \frac{1}{4\pi\epsilon_0} 
\left[
\oint_{\partial \mathcal V} \frac{1}{\mathscr r} \vec P\cdot d \vec a' -
\int_\mathcal V \frac{1}{\mathscr r}\nabla'\cdot \vec P d \tau'
\right]\\
\end{align}
$$
These integrals look like what we would expect from a surface charge density and a volume charge density respectively. By defining the surface bound charge $\sigma_b \equiv \vec P \cdot \hat n$ and the volume bound charge $\rho_b \equiv -\nabla \cdot \vec P$ we can make this observation official.
$$
\begin{align}
V&= \frac{1}{4\pi\epsilon_0} 
\left[
\oint_{\partial \mathcal V} \frac{\sigma_b}{\mathscr r}  da' -
\int_\mathcal V \frac{\rho_b}{\mathscr r} d \tau'
\right]\\
\end{align}
$$
Thus the electric field produced by a total polarization is equivalent to if there were the above charges present within the material allowing us to use all our powerful tools like Gauss's law
### Physical interpretation
Bound charges accumulate on the surface of the object
![[Pasted image 20260701113527.png|500]]
Charges are generated at sources and sinks within a material
![[Pasted image 20260701113647.png|400]]
## Free charges
Say that our material was not just neutral with a polarization but instead also had charges placed within it according to $\rho_f$. Then Gauss's law reads
$$
\begin{align}
\epsilon_0 \nabla \cdot \vec E &= \rho \\
&= \rho_b + \rho_f \\
&= -\nabla \cdot \vec P+ \rho_f \\
\nabla \cdot (\epsilon_0 \vec E) + \nabla \cdot \vec P&= \rho_f \\
\nabla \cdot (\epsilon_0 \vec E + \vec P) &= \rho_f \\
\end{align}
$$
This quantity $\vec D = \epsilon_0 \vec E + \vec P$ is called the electric displacement and has very similar properties to the electric field except it only operates based off of $\rho_f$. Note that the $\vec E$ that appears in this equation is in fact the total electric field including the effects of polarization.

In the same way as the electric field $\vec D$ follows the integral version of Gauss's law
$$
\begin{align}
\oint \vec D \cdot d\vec A &= q_{f_{\text{enc}}}
\end{align}
$$
### Example use case
Consider an infinite wire enclosed in a rubber cylindrical casing with radius $a$. To find the electric field inside and outside of the wire we can use the displacement.

Consider the Gaussian cylinder with length $L$ and radius $s$ then by Gauss's law:
$$
\begin{align}
\oint \vec D \cdot d\vec A = q_{f_{\text{enc}}} \\
D\oint d A = \lambda L \\
D2\pi sL = \lambda L \\
\vec D = \frac{\lambda}{2\pi s} \hat s\\
\end{align}
$$
We can then use that $\vec D = (\epsilon_0 \vec E + \vec P)$ to find $\vec E$ if we were to know $\vec P$. For air $\vec P = 0$ thus
$$
\begin{align}
\vec E_{\text{outside}} &= \frac{\lambda}{2\pi \epsilon_0 s}\hat s
\end{align}
$$
as we got when there was not rubber case.