## The big picture
Previously we discussed the Lagrangian approach to classical mechanics where given a state space of our system with coordinates $q_i$ we can construct an object called the Lagrangian $\mathcal L(q_i, \dot q_i, t)$ and the equation of motion of our particle through this state space is given by the Euler-Lagrange equations.

In the Lagrangian approach, for every point in state space there in an infinite number of trajectories that a particle can follow that pass through that point

In Hamilton's approach we define a $2N$ dimensional space by appending the canonical momentum to our state space to produce what we call a **phase space** with coordinates $q_i, p_i$.  

In this **phase space** every point has only one trajectory and so there must be a "flow" in this phase space. Finding this flow is what **Hamiltonian mechanics** sets out to do.

## The Hamiltonian
The Hamiltonian is defined as
$$
\begin{align}
\mathcal H = \sum_{i} p_i\dot q_i  - \mathcal L
\end{align}
$$
## Hamilton's equations
Consider the 1d case:
Assuming a conservative system we get that $\mathcal L$ is given by
$$
\begin{align}
\mathcal L &= \mathcal L(q, \dot q) \\
&= T - U \\
&= \frac{1}{2} A(q)\dot q^2 - U(q)
\end{align}
$$
The generalized momentum is then given by
$$
\begin{align}
p &= \frac{\partial \mathcal L}{\partial \dot q} \\
&= A(q)\dot q
\end{align}
$$
This implies that $\dot q$ is a function of $p$ and $q$ and thus we can write our Hamiltonian as a function of $q$ and $p$
$$
\begin{align}
\mathcal H(p, q) = p \dot q(p, q) - \mathcal L \left(q, \dot q(p, q)\right)
\end{align}
$$
Now considering the derivatives of $\mathcal H$ we get:
$$
\begin{align}
\frac{\partial \mathcal H}{\partial q} &= p \frac{\partial \dot q}{\partial q} - \left[\frac{\partial \mathcal L}{\partial q} + \frac{\partial \mathcal L}{\partial \dot q}\frac{\partial \dot q}{\partial q}\right] \\
 &= p \frac{\partial \dot q}{\partial q} -\frac{\partial \mathcal L}{\partial q} - p\frac{\partial \dot q}{\partial q} \\
 &= - \frac{\partial \mathcal L}{\partial q}\\
 &= - \frac{dp}{dt}\\
&= -\dot p \\
\frac{\partial \mathcal H}{\partial p} &= \dot q + p\frac{\partial \dot q}{\partial p} - \frac{\partial \mathcal L}{\partial \dot q} \frac{\partial \dot q}{\partial p} \\
 &= \dot q + p\frac{\partial \dot q}{\partial p} - p \frac{\partial \dot q}{\partial p} \\
 &= \dot q\\
\end{align}
$$
These two first order ODE's are known as **Hamilton's equations** and they describe the flow of phase space.

$$
\begin{equation}
\boxed{
\begin{aligned}
\frac{\partial \mathcal H}{\partial q} &= -\dot p \\
\frac{\partial \mathcal H}{\partial p} &= \dot q \\
\end{aligned}
}
\end{equation}
$$

