## The state before Maxwell
Before Maxwell there were 4 well known laws:
$$
\begin{align}
\vec \nabla \cdot \vec E &= \frac{\rho}{\epsilon_0} & \text{(Gauss's law)} \\
\vec \nabla \cdot \vec B &= 0 & \text{(No Magnetic Monopoles)} \\
\vec \nabla \times \vec E &= -\frac{\partial \vec B}{\partial t} & \text{(Faraday's Law)} \\
\vec \nabla \times \vec B &= \mu_0 \vec J & \text{(Ampere's Law)}
\end{align}
$$
These laws were great however Maxwell found a problem
## Charge conservation
Consider Ampere's Law:
$$
\begin{align}
\vec \nabla \times \vec B &= \mu_0 \vec J
\end{align}
$$
Then take the divergence of both sides to get:
$$
\begin{align}
\vec \nabla \cdot \left[\vec \nabla \times \vec B\right] &= \mu_0 \vec \nabla \cdot \vec J \\
0 &= \mu_0 \vec \nabla \cdot \vec J \\
\end{align}
$$
This would indicate that the divergence of $\vec J$ is 0 however it is totally physical for charges to be flowing out from a point. To account for this it should instead be the continuity equation
$$
\begin{align}
\vec \nabla \cdot \vec J + \frac{\partial \rho}{\partial t} &= 0
\end{align}
$$
Maxwell realized this and thus fixed Ampere's law. To do this ourselves we work backwards noticing that $\rho = \epsilon_0 \vec \nabla \cdot \vec E$ and thus our fixed equation becomes:
$$
\begin{align}
0 &= \mu_0 \left(\vec \nabla \cdot \vec J + \epsilon_0 \vec \nabla \cdot \frac{\partial \vec E}{\partial t}\right) \\
\vec \nabla \cdot \left[\vec \nabla \times \vec B\right] &= \mu_0\vec \nabla \cdot \left(\vec J + \epsilon_0 \frac{\partial \vec E}{\partial t}\right)\\
\vec \nabla \times \vec B &= \mu_0\vec J + \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t}\\
\end{align}
$$
Thus is the called the Ampere-Maxwell equation and completes Maxwell's equations.
## CGS Units
CGS (centimeter, gram, second) units are common when working with electricity and magnetism and in these units the equations become:
$$
\begin{align}
\vec \nabla \cdot \vec E &= 4\pi \rho \\
\vec \nabla \cdot \vec B &= 0 \\
\vec \nabla \times \vec E &= -\frac{1}{c} \frac{\partial \vec B}{\partial t} \\
\vec \nabla \times \vec B &= \frac{1}{c}\left(4\pi \vec J + \frac{\partial \vec E}{\partial t}\right)
\end{align}
$$
<% tp.file.cursor(2) %>