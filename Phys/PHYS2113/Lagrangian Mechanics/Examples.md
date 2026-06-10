## Planar Pendulum
![[Pasted image 20260609153807.png]]
We have a mass attached to the end of a fixed mass-less rod which has length $l$ and who's other end is attached to a fixed point. There is gravity.

The most natural coordinate system to chose here is the angle the rod makes with the perpendicular $\alpha$
$$
\begin{align}
\mathcal L &= \frac{1}{2}ml^2\dot \alpha^2 - mgl(1 - \cos\alpha) \\
\mathcal L &= \frac{1}{2}ml^2\dot \alpha^2 - mgl + mgl\cos\alpha \\
\end{align}
$$
Then by the EL equations:
$$
\begin{align}
\frac{d}{dt}(ml^2\dot \alpha) &= -mgl\sin\alpha \\
ml^2\ddot \alpha &= -mgl\sin\alpha \\
\ddot \alpha &= -\frac{g}{l}\sin\alpha \\
\end{align}
$$
## Atwood machine
![[Pasted image 20260609153910.png]]
We want to find a coordinate system with the least amount of parameters that can still span the configuration space of the entire system. In this case, the rope is a fixed distance so $y = L - x$.
Then lets use $x$ as our generalized coordinate. This gives
$$
\begin{align}
\mathcal L(x, \dot x, t) &= \frac{1}{2}m_1\dot x^2 + \frac{1}{2}m_2\dot x^2 - m_1g(L - x) - m_2gx \\
&= \frac{1}{2}(m_1 + m_2) \dot x^2 - m_1gL   + g(m_1 - m_2)x \\
\end{align}
$$
Then the EL equations give:
$$
\begin{align}
\frac{d}{dt}((m_1 + m_2) \dot x) &= g(m_1 - m_2) \\
(m_1 + m_2) \ddot x &= g(m_1 - m_2) \\
\ddot x &= g\frac{m_1 - m_2}{m_1 + m_2}
\end{align}
$$

