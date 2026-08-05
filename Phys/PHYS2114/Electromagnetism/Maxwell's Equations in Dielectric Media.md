## Maxwell's Equations in a Media
In a vacuum Maxwell's equations can be written:
$$
\begin{align}
\vec \nabla \cdot \vec E &= \frac{\rho}{\epsilon_0} \\
\vec \nabla \cdot \vec B &= 0 \\
\vec \nabla \times \vec E &= -\frac{\partial \vec B}{\partial t} \\
\vec \nabla \times \vec B &= \mu_0\vec J + \mu_0 \epsilon_0 \frac{\partial \vec E}{\partial t}
\end{align}
$$
but it is equally as common to define two new vector fields
$$
\begin{align}
\vec D &= \epsilon_0 \vec E \\
\vec B &= \mu_0 \vec H
\end{align}
$$
and thus write Maxwell's equations as:
$$
\begin{align}
\vec \nabla \cdot \vec D &= \rho \\
\vec \nabla \cdot \vec B &= 0 \\
\vec \nabla \times \vec E &= -\frac{\partial \vec B}{\partial t} \\
\vec \nabla \times \vec H &= \vec J + \frac{\partial \vec D}{\partial t}
\end{align}
$$
With this we can transfer between media very easily by redefining $\vec D, \vec H$ in the media as
$$
\begin{align}
\vec D &= \epsilon_0\epsilon \vec E \\
\vec B &= \mu_0 \mu \vec H
\end{align}
$$
and our Maxwell equations remain as above. Importantly $\rho$ and $\vec J$ are only for external charges in these equations as the internal charges are encapsulated by the $\epsilon$ and $\mu$ terms.
