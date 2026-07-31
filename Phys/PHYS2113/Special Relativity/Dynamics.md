## The displacement vector
Consider the differential of our 4-vector for position:
$$
\begin{align}
dx &= (dx^0, dx^1, dx^2, dx^3) \\
&= (c, \vec v) dt
\end{align}
$$
In the particle's rest frame $\vec v = 0$  thus $dx$ is timelike and $c^2 > v^2$ thus we get that all particles with $dt > 0$ (all particles with mass) move slower than light.

## Quotient Rule
The Quotient rule helps us determine if some quantity is indeed a 4-vector. The rule states:

A vector with 4 components is a 4-vector if for a known 4-vector $x$ $x^\mu k_\mu$ is invariant in all reference frames

## Relativistic Doppler effect
We know that a wave has the equation $V = \cos(\vec k \cdot \vec x - \omega t - \delta)$ where $|\vec k| = \frac{2\pi}{\lambda}$ and $v = \frac{\omega}{|\vec k|}$. Ignoring the phase shift this looks like the scalar product of two 4-vectors:
$$
\begin{align}
k &= (-\frac{\omega}{c}, \vec k) \\
x &= (ct, x, y, z)
\end{align}
$$
The 2nd vector is obviously a 4-vector so lets test if $k$ is also a 4-vector. The Quotient rule states that if $k^\mu x_\mu$ is invariant in all reference frames then $k$ is indeed a 4-vector and thus transforms like one. Obviously the value of the wave at a specific point in space time should be constant no matter the reference frame and thus the scalar product should be invariant thus $k$ is a 4-vector.

This implies that going from one frame to another $k$ transforms via a Lorentz boost. Assuming that the wave is traveling in the $x$ direction and we are going to a reference frame traveling in the same direction we get:
$$
\begin{align}
k' &= \gamma \pmatrix{1 &-\beta \\ - \beta & 1} k \\
- \frac{\omega'}{c} &= \gamma(-\frac{\omega}{c} - \beta k^1) \\
\omega' &= \gamma\omega + c\gamma\beta k^1 \\
\omega' &= \gamma\omega + \gamma v k^1 \\

\end{align}
$$
## Invariant Mass
In SR mass has no concencus meaning, instead it is defined in one of two ways:
- invariant mass
- variant mass
In this course we will only use the invariant definition of mass which is simply the normal mass of the object in a rest frame. Due to this definition being the same throughout all reference frames this makes the mass $m$ a **Lorentz scalar**
## 4-Velocity
The usual velocity vector $\frac{dx}{dt}$ is a bit awkward in SR as velocity addition is weird and it is not a 4-vector. To fix this we want to instead differentiate w.r.t an invariant in order to preserve the 4-vector-ness of the position vector. To do this we shall use the proper time $t_0 = \tau$.

The displacement vector is given by:
$$
\begin{align}
dx = (c, \vec v)dt
\end{align}
$$
Using a rest frame the line element of the displacement is $c^2 d\tau^2$ whist the line element in a general frame is $(c^2 - v^2)dt^2$  thus we have that:
$$
\begin{align}
d\tau^2 &= \left(1 - \frac{v^2}{c^2}\right)dt^2 \\
d\tau &= \sqrt{1 - \frac{v^2}{c^2}}dt \\
d\tau &= \frac{dt}{\gamma} \\
\frac{dt}{d\tau} &= \gamma
\end{align}
$$
This is an interesting result and we shall use it to find the derivatives of the other components w.r.t the proper time.
$$
\begin{align}
\frac{dx^i}{d\tau} &= \frac{dx^i}{dt}\frac{dt}{d\tau} \\
&= v_i\gamma
\end{align}
$$
thus our 4-velocity is:
$$
\begin{align}
\frac{dx^\mu}{d\tau} &= \gamma \frac{dx^\mu}{dt} \\
\frac{dx}{d\tau} &= \gamma(c, \vec v)
\end{align}
$$
