In Lagrangian mechanics we define the difference between the Kinetic energy $T$ and the potential energy $U$ as the **Lagrangian** $\mathcal L = T - U$. The integral if this object w.r.t time is the action:
$$
\begin{align}
S = \int\mathcal L(q_i, \dot q_i, t) dt
\end{align}
$$
and the path any particle takes is the one which extreamizes the action and thus we find our equations of motion with the E-L equation
$$
\begin{align}
\frac{d}{dt} \frac{\partial \mathcal L}{\partial \dot q_i} &= \frac{\partial \mathcal L}{\partial q_i}
\end{align}
$$
## Relation to Newtonian particles
Consider a point particle in a cartisian inertial reference frame, thus
$$
\begin{align}
\mathcal L &= T - U \\
&= \frac{1}{2} mv^2 - U \\
&= \frac{1}{2} m(\dot x^2 + \dot y^2 + \dot z^2) - U(x, y, z)
\end{align}
$$
Then,
$$
\begin{align}
\frac{d}{dt}\left (\frac{\partial \mathcal L}{\partial \dot q_i}\right) &= \frac{\partial \mathcal L}{\partial q_i} \\
\frac{d}{dt}\left(m\dot q_i \right) &= -\frac{\partial U}{\partial q_i} \\
m\ddot q_i  &= F_i \\
m\ddot a_i  &= F_i \\
\vec F &= m \vec a\\
\end{align}
$$
omg that is Newton!

##

