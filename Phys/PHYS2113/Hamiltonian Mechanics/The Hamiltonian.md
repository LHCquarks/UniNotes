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
Assuming a conservative system we get that $\mathcal L$ is given by
$$
\begin{align}
\mathcal L &= \mathcal L(q_i, \dot q_i) \\
&= T - U \\
&= \frac{1}{2} A(q_j)\dot q_i^2 - U(q_i)
\end{align}
$$
The generalized momentum is then given by
$$
\begin{align}
p_i &= \frac{\partial \mathcal L}{\partial \dot q_i} \\
&= A(q_j)\dot q_i
\end{align}
$$
This implies that $\dot q_i$ is a function of $p_i$ and $q_j$ and thus we can write our Hamiltonian as a function of $q_j$ and $p_i$
$$
\begin{align}
\mathcal H(p_i, q_i) = \sum_i p_i \dot q_i(p_i, q_j) - \mathcal L \left(q_i, \dot q_i(p_i, q_j)\right)
\end{align}
$$
Now considering the derivatives of $\mathcal H$ we get:
$$
\begin{align}
\frac{\partial \mathcal H}{\partial q_i} &= \sum_jp_j\frac{\partial \dot q_j}{\partial q_i} - \left[\frac{\partial \mathcal L}{\partial q_i} + \sum_j\frac{\partial \mathcal L}{\partial \dot q_j}\frac{\partial \dot q_j}{\partial q_i}\right] \\
 &= \sum_jp_j \frac{\partial \dot q_j}{\partial q_i} - \frac{\partial \mathcal L}{\partial q_i} - \sum_jp_j\frac{\partial \dot q_j}{\partial q_i} \\
 &= - \frac{\partial \mathcal L}{\partial q_i}\\
 &= - \frac{dp_i}{dt}\\
&= -\dot p_i \\
\frac{\partial \mathcal H}{\partial p_i} &= \dot q_i + p_i\frac{\partial \dot q_i}{\partial p_i} - \frac{\partial \mathcal L}{\partial \dot q_i} \frac{\partial \dot q_i}{\partial p_i} \\
 &= \dot q_i + p_i\frac{\partial \dot q_i}{\partial p_i} - p_i \frac{\partial \dot q_i}{\partial p_i} \\
 &= \dot q_i\\
\end{align}
$$
These two first order ODE's are known as **Hamilton's equations** and they describe the flow of phase space.

$$
\begin{equation}
\boxed{
\begin{aligned}
\frac{\partial \mathcal H}{\partial q_i} &= -\dot p_i \\
\frac{\partial \mathcal H}{\partial p_i} &= \dot q_i \\
\end{aligned}
}
\end{equation}
$$

These equations hold in all situations even with non-conservative fields