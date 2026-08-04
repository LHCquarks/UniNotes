## Energy Flux
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
## Energy flows outside of wires
Consider a straight coaxial cable of two metal cylinders. The inner circle has voltage $V$ (D.C) whilst the outer circle is grounded.
![[Pasted image 20260804173304.png]]
We know the electric field is radial and so we can use Gauss's law with a cylindrical Gaussian surface of length $l$ and radius $a < r$:
$$
\begin{align}
\int_S \vec E \cdot d\vec A &= \frac{\rho}{\epsilon_0} \\
E\int_S d\vec A &= \frac{\lambda  l}{\epsilon_0} \\
E 2\pi rl &= \frac{\lambda  l}{\epsilon_0} \\
E &= \frac{\lambda}{2\pi r\epsilon_0} \\
\vec E &= \frac{\lambda}{2\pi r\epsilon_0} \hat r \\
\end{align}
$$
For $r < a$ it can be shown that $\vec E = 0$.

To find $\lambda$ we need to consider the voltage between the two cylinders:
$$
\begin{align}
V &= \int \vec E \cdot d\vec l \\
&= \int_a^b E  dr \\
&= \int_a^b \frac{\lambda}{2\pi r\epsilon_0} dr \\
&= \frac{\lambda}{2\pi \epsilon_0} \ln\left(\frac{b}{a}\right) \\
\lambda &= \frac{2\pi\epsilon_0V}{\ln\left(\frac{b}{a}\right)}
\end{align}
$$
and thus
$$
\begin{align}
\vec E &= \frac{V}{\ln\left(\frac{b}{a}\right)r} \hat r
\end{align}
$$
Now for the magnetic field we know it is in the $\hat \theta$ direction and thus we will define an Amperian loop as a circle centered with the cable and with a radius $r$. 
If $a < r < b$ then 
$$
\begin{align}
\int \vec B \cdot d\vec l &= \mu_0 I_\text{enc} \\
B \int dl &= \mu_0I \\
B &= \frac{\mu_0I}{2\pi r} \\
\vec B &= \frac{\mu_0I}{2\pi r} \hat \theta
\end{align}
$$
In the case where $b < r$ we get
$$
\begin{align}
\int \vec B \cdot d\vec l &= \mu_0 I_\text{enc} \\
B \int dl &= 0 \\
\vec B &= 0 \\
\end{align}
$$
Finally, if $r < a$ we get
$$
\begin{align}
\int \vec B \cdot d\vec l &= \mu_0 I_\text{enc} \\
B \int dl &= 0 \\
\vec B &= 0 \\
\end{align}
$$
Finally we can calculate the Poynting vector:

$$
\begin{align}
\vec S &= \frac{1}{\mu_0} \left[\vec E \times \vec B\right] \\
\text{for } r < a \ \ \ \ \ \ &\\
\vec S &= 0 \\
\text{for } a < r < b \ \ \ \ \ \ &\\
\vec S &=  \frac{1}{\mu_0} \frac{V}{\ln\left(\frac{b}{a}\right) r}\frac{\mu_0I}{2\pi r} \hat z \\
\text{for } b < r \ \ \ \ \ \ &\\
\vec S &= 0 \\
\end{align}
$$

So the energy flows outside of the wire ($a < r < b$). The magnitude of this energy transfer is then
$$
\begin{align}
\vec S &= \frac{VI}{2\pi\ln\left(\frac{b}{a}\right)r^2} \hat z \\
\mathcal P &= \int \vec S \cdot d\vec A \\
&= \int \frac{VI}{2\pi\ln\left(\frac{b}{a}\right)r^2} dA \\
&= \int \frac{VI}{2\pi\ln\left(\frac{b}{a}\right)r^2} rdrd\theta \\
&= \frac{VI}{2\pi \ln\left(\frac{b}{a}\right)} [\theta]_0^{2\pi} \int_a^b \frac{1}{r} dr \\
&= \frac{VI}{\ln\left(\frac{b}{a}\right)} \left[\ln\left(r\right)\right]_a^b \\
&= \frac{VI}{\ln\left(\frac{b}{a}\right)} \ln\left(\frac{b}{a}\right) \\
&= VI \\

\end{align}
$$
Which agrees with conventional theory.