## Coulombs law
According to Coulomb, the force between two charged particles is given by:
$$
\begin{align}
\vec F = \frac{1}{4\pi\epsilon_0}\frac{q_1q_2}{r^2} \hat r
\end{align}
$$
## Point particle electric field
The electric field is defined such that for any particle of charge $q$ we have that
$$
\begin{align}
\vec F = q\vec E
\end{align}
$$
Thus the formula for the electric field for a point particle is:
$$
\begin{align}
\vec E = \frac{1}{4\pi\epsilon_0}\frac{q}{r^2} \hat r
\end{align}
$$
## Discrete charge distributions
If we have a discrete set of particles then we can simply find the electric field produced by each particle and sum them together like so:
$$
\begin{align}
\vec E &= \sum_{i = 0}^N \vec E_i \\
&= \frac{1}{4\pi\epsilon_0} \sum_{i = 0}^N \frac{q_i}{r_i^2}\hat r_i\\
\end{align}
$$
## Continuous charge distributions
For the continuous case we are given a charge density $\rho(\vec x)$. 
We will consider the electric field caused from a infinitesimal part of the charge distribution and sum them all up with an integral.
We replace $q =  \rho(\vec x) d\vec x$ then the electric field at a point $\vec x_0$ is given by:
$$
\begin{align}
\vec E = \frac{1}{4\pi \epsilon_0} \int \frac{\rho(\vec x) d\vec x}{|\vec x - \vec x_0|^2} \frac{\vec x - \vec x_0}{|\vec x - \vec x_0|}
\end{align}
$$
### Example
Say we have a loop with a linear charge density $\lambda$ with radius $r$. Find $\vec E$ from a distance $z$ above the center of the loop. The setup is shown below
![[Pasted image 20260601141248.png]]
Consider an infinitesimal segment along the loop $ds$, then the electric field of that part is given by:
$$
\begin{align}
dE = \frac{1}{4\pi\epsilon_0}\frac{\lambda ds}{r^2 + z^2}
\end{align}
$$
Now, when we rotate around the loop we know all but the vertical components of the $\vec E$ field will be canceled out. The vertical components of the field will be given by:
$$
\begin{align}
dE = \frac{1}{4\pi\epsilon_0}\frac{\lambda ds}{r^2 + z^2} \cos \theta
\end{align}
$$
where $\theta$ is the angle made between the $z$ axis and the $dE$ vector. However it can fairly easily be seen that $\cos \theta = \frac{z}{\sqrt{r^2 + z^2}}$ and thus:
$$
\begin{align}
dE = \frac{1}{4\pi\epsilon_0} \frac{\lambda zds}{(r^2 + z^2)^{3/2}}
\end{align}
$$
Finally, we sum over the entire $ds$ to get:
$$
\begin{align}
E &= \int_0^{2\pi} \frac{1}{4\pi\epsilon_0} \frac{\lambda zds}{(r^2 + z^2)^{3/2}} \\
&= \frac{2\pi}{4\pi\epsilon_0} \frac{\lambda z}{(r^2 + z^2)^{3/2}} \\
&= \frac{1}{2\epsilon_0} \frac{\lambda z}{(r^2 + z^2)^{3/2}} \\
\end{align}
$$
<% tp.file.cursor(2) %>