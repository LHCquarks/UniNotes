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
## 4-Energy
Consider an atom that is stationary in frame $\mathcal S$ that emits two photons in opposite directions.
![[Pasted image 20260804141814.png]]
In the $\mathcal S$ frame the atom initially had energy $E_0$ and afterwards had energy $E_1 = E_0 - \Delta E$.

In the frame $\mathcal S'$ moving at a velocity of $v$ relative to $\mathcal S$ we experience a Doppler shift in the photons.
In this reference frame the initial and final energy is given by $E_1' = E_0' - \Delta E'$.

Using the Doppler shift formula we can get $\Delta E'$ in terms of $\Delta E$:
$$
\begin{align}
\Delta E' &= \sqrt{\frac{1 + \beta}{1 - \beta}}\left(\frac{\Delta E}{2}\right) + \sqrt{\frac{1 - \beta}{1 + \beta}}\left(\frac{\Delta E}{2}\right) \\
&= \gamma \Delta E
\end{align}
$$
This is different from the stationary frame. 

To recap we have the two equations
$$
\begin{align}
E_1 &= E_0 - \Delta E \\
E_1' &= E_0' - \gamma \Delta E
\end{align}
$$
Combining these equations we get
$$
\begin{align}
(E_0' - E_0) - (E_1' - E_1) = (\gamma - 1) \Delta E
\end{align}
$$
Now, notice that because the atom is moving in $\mathcal S'$ it must have kinetic energy which we write as
$$
\begin{align}
T_0' &= E_0' - E_0 \\
T_1' &= E_1' - E_1
\end{align}
$$
and hence
$$
\begin{align}
T_0' - T_1' &= (\gamma - 1) \Delta E
\end{align}
$$
There is nothing special about this setup so energy transforms via 
$$
\begin{align}
E' &= \gamma E
\end{align}
$$

## 4-Momentum
Now that we have our 4-velocity we can define our 4-momentum as
$$
\begin{align}
p &= m\frac{dx}{d\tau} \\
&= m\gamma(c, \vec v)
\end{align}
$$
where $m$ is our rest mass. Further, this implies that our old 3-momentum is $m\gamma \vec v$.

Sometimes $m\gamma$ is packaged up into another term $m_\text{rel}$ however this is not a drop in replacement for classical mechanics and so we will not work with it.

It is clear that the the time component of our 4-momentum is the energy of our particle
$$
\begin{align}
p^0 &= E/c \\
p &= (E / c, m\gamma \vec v)
\end{align}
$$
### $E = mc^2$ in its full glory
Because this momentum vector is a 4-vector it is linear and their length squared is invariant in all reference frames. Thus $E^2 / c^2 - p^2$ is invariant and because $c$ is invariant we get the prettier result
$$
\begin{align}
E^2 - p^2c^2 = (E')^2 - (p')^2c^2
\end{align}
$$

For a material particle in it's rest frame $p_0 = (mc, 0, 0, 0)$ and thus for all reference frames
$$
\begin{align}
m_0^2 c^4 &= E^2 - p^2c^2 \\
E^2 &= m_0^2c^4 + p^2c^2
\end{align}
$$
### Conservation of momentum
As in Newtonian mechanics momentum and energy are conserved however this just means

