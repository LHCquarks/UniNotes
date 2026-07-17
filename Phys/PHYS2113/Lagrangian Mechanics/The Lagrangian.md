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
## Hamilton's principle
Hamilton's principle is:

"The trajectory $\vec x(t)$ of a particle moving from point $P_1 = \vec x(t_0)$ to $P_2 = \vec x(t_1)$ in configuration space is such that the action is stationary" 

But the trajectory of a particle is a physical quantity so it should not depend on the coordinate system used and thus the Euler Lagrange equation work for arbitrary coordinate systems which make Lagrangian mechanics far more general than Newtonian ($F \not = m\ddot q_i$ in general).
## Generalized Force and Generalized Momentum
$$
\begin{align}
\frac{d}{dt} \frac{\partial \mathcal L}{\partial \dot q} &= \frac{\partial \mathcal L}{\partial q}
\end{align}
$$
Because in Cartesian coordinates, the RHS of the EL equation produces the force and the partial in the LHS produces the momentum we call these quantities the **generalized momentum** and **generalized force**:
$$
\begin{align}
p &= \frac{\partial \mathcal L}{\partial \dot q} \\
F &= \frac{\partial \mathcal L}{\partial q} \\
\end{align}
$$
## Polar example
In polar coordinates we have that $\vec v = \dot r \vec e_r + r \dot \theta \vec e_\theta$, therefore:
$$
\begin{align}
\mathcal L &= \frac{1}{2} m \vec v^2 - U(r, \theta) \\
&= \frac{1}{2} m (\dot r^2 + r^2 \dot \theta^2) - U(r, \theta) \\
\end{align}
$$
And using the E-L equations for $r$:
$$
\begin{align}
\frac{d}{dt} \frac{\partial \mathcal L}{\partial \dot r} &= \frac{\partial \mathcal L}{\partial r} \\
\frac{d}{dt} \left(m\dot r\right)  &= mr\dot \theta^2 - \frac{\partial U}{\partial r} \\
m\ddot r  &= mr\dot \theta^2 + F_r \\
F_r &= m(\ddot r - r\dot \theta^2) \\
\end{align}
$$
and for $\theta$:
$$
\begin{align}
\frac{d}{dt} \frac{\partial \mathcal L}{\partial \dot \theta} &= \frac{\partial \mathcal L}{\partial \theta} \\
\frac{d}{dt}(m\dot \theta r^2) &= -\frac{\partial U}{\partial \theta} \\
r F_\theta &= \frac{d}{dt}(m\dot \theta r^2) \\
\vec \tau &= \frac{d}{dt} \vec L \\
\end{align}
$$
## More than one particle
Given more than one particle we can simply consider the total Kinetic and Potential of the of the system to find the Lagrangian:
$$
\begin{align}
\mathcal L \left(q_i^j, \dot q_i^j, t\right)
\end{align}
$$

