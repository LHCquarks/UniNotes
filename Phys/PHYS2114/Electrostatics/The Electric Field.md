## What is the electric field
The goal of electrostatics if to find the force exerted by an arbitrary charge distribution on other particles. The charge exerted by a charged object it proportional to the charge of the object experiencing the force $\vec F \propto Q$. We denote the proportionality constant the electric field $\vec E$ so that
$$
\begin{align}
\vec F = Q \vec E
\end{align}
$$
## Coulomb's law
Coulomb's law for forces states that for a single point charge
$$
\begin{align}
\vec F &= \frac{1}{4\pi\epsilon_0}\frac{qQ}{\mathscr r^2} \hat {\mathscr r}
\end{align}
$$
Where:
- $\vec F$ is the force exerted on the particle
- $\epsilon_0$ is the electric permittivity of free space and is given by $\epsilon_0 = 8.85\times10^{-12}\frac{C^2}{Nm^2}$
- $q$ is the charge of the point charge
- $Q$ is the charge of the object experiencing the force
- $\vec{\mathscr r}$ is the displacement vector from the point charge to our object experiencing the force $\vec{\mathscr r} = \vec r - \vec r'$ 

We can then use the definition of the electric field to to get that for a point charge
$$
\begin{align}
\vec E &= \frac{1}{4\pi\epsilon_0}\frac{q}{\mathscr r^2} \hat {\mathscr r}
\end{align}
$$
## Superposition
The total electric force that an object experiences from multiple point charges obeys the law of superposition so that $F_{\text{total}} = F_1 + F_2 + F_3 + \dots$. This is important as it allows us to find the force on any particle due to a collection of charges. Further, this law of superposition carries over to the electric field and thus
$$
\begin{align}
\vec E_{\text{total}}(\vec r) &= \sum_{i}\frac{1}{4\pi\epsilon_0}\frac{q_i}{\mathscr r_i^2} \hat {\mathscr{r}_i}
\end{align}
$$
## Continuous charge distributions
For a continuous charge distribution we simply convert the summation sign into an integral sign like so:
$$
\begin{align}
\vec E &= \int \frac{1}{4 \pi \epsilon_0} \frac{dq}{\mathscr r^2} \hat{\mathscr r}
\end{align}
$$
Now, we have some different expressions for $dq$ depending on what dimension we are working in but they basically amount to the same idea:
- 1d gives $dq = \lambda dl$
- 2d gives $dq = \sigma dA$
- 3d gives $dq = \rho d\tau$
Further, because in the integral we are varying over $\vec r'$ we add a $'$ to our differential to get for 3d
$$
\begin{align}
\vec E &= \frac{1}{4\pi\epsilon_0} \int \frac{\rho(\vec r')}{\mathscr r^2} \hat {\mathscr r} d\tau' \\
\vec E(\vec r) &= \frac{1}{4\pi\epsilon_0} \int \frac{\rho(\vec r')}{|\vec r - \vec r'|^3} (\vec r - \vec r') d\tau'
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
\vec E &= \int_0^{2\pi} \frac{1}{4\pi\epsilon_0} \frac{\lambda zds}{(r^2 + z^2)^{3/2}} \hat k\\
&= \frac{2\pi r}{4\pi\epsilon_0} \frac{\lambda z}{(r^2 + z^2)^{3/2}} \hat k\\
&= \frac{1}{2\epsilon_0} \frac{\lambda z r}{(r^2 + z^2)^{3/2}} \hat k\\
\end{align}
$$
## Gauss's law
The process of integration outlined above can be quite tedious and hard so where symmetry allows we can use Gauss's law to simplify our working.

Gauss's law states that the total electric flux over any surface is entirely determined by the total charge enclosed within the object:
$$
\begin{align}
\oint_S \vec E \cdot d\vec A &= \frac{q_{\text{enc}}}{\epsilon_0}
\end{align}
$$
### Example
Consider a sphere with a uniform charge distribution $\rho$ and a radius of $R$. Then we can consider different spheres centered at the center the charged sphere with the various radii $r$.

Because of the symmetries of our setup, $\vec E$ is always parallel to our $d\vec A$ and is constant across our sphere and thus 
$$
\begin{align}
\oint_S E d A &= \frac{q_{\text{enc}}}{\epsilon_0} \\
E \oint_S d A &= \frac{q_{\text{enc}}}{\epsilon_0} \\
E 4\pi r^2 &= \frac{q_{\text{enc}}}{\epsilon_0} \\
\end{align}
$$
If $r > R$ then $q_{\text{enc}} = \rho \frac{4}{3}\pi R^3$ so we get that:
$$
\begin{align}
E &= \frac{\rho R^3}{3\epsilon_0r^2} \\
\vec E &= \frac{\rho R^3}{3\epsilon_0r^2}\hat r \\
\end{align}
$$
If on the other hand $r < R$ then $q_{\text{enc}} = \rho \frac{4}{3}\pi r^3$ and thus:
$$
\begin{align}
E &= \frac{\rho r^3}{3 \epsilon_0 r^2} \\
\vec E&= \frac{\rho r}{3 \epsilon_0} \hat r
\end{align}
$$
