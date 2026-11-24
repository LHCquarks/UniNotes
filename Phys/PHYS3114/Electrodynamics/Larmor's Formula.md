Consider a point charge moving around according to $\vec r_q(t')$ then the charge and current densities are given by:
$$
\begin{align}
\rho(\vec r', t') &= q\delta(\vec r' - \vec r_q(t')) \\
\vec J(\vec r', t') &= q\dot r_q(t') \delta(\vec r' - \vec r_q(t'))
\end{align}
$$
Then by we can start by finding the electric di-pole
$$
\begin{align}
\vec p(t') &= \int_{\mathbb R^3} \rho (\vec r', t') \vec r' d^3r' \\
&= q\int_{\mathbb R^3} \delta(\vec r' - \vec r_q(t')) \vec r' d^3 r' \\
&= q \vec r_q(t') \\
\end{align}
$$
Because this exists the remaining terms are negligible compared to it so we can just use the dipole term for radiated power:
$$
\begin{align}
\mathcal P &= \frac{\mu_0\ddot p^2}{6\pi c} \\
&= \frac{\mu_0 q^2 \ddot r_q}{6\pi c} \\
&= \frac{\mu_0 q^2 a^2(t - r/c)}{6\pi c}
\end{align}
$$
