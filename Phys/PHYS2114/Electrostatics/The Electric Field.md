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

