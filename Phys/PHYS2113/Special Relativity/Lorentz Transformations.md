So far we have discussed transforming our $\Delta t$ between two reference frames that include a proper time reference frame, and similar for $\Delta l$ but what are we meant to do generally?

This is what Lorentz transformations are for

## The Lorentz transform
Given two inertial F.O.R, $\mathcal S$ and $\mathcal S'$ and assuming that the velocity of $\mathcal S'$ rel to $\mathcal S$, $v$ is in the $x$ direction we get the general formulas
$$
\begin{align}
t' &= \gamma \left(t - v\frac{x}{c^2}\right) \\
x' &= \gamma \left(x - vt\right) \\
y' &= y \\
z' &= z \\
\end{align}
$$
and the inverse transform is given by substituting in $-v$ instead of $v$
## Simultaneity
Consider the following Gedanken experiment:

One person is carrying a ladder ($l_0 = 2$m) at $v = \sqrt{3}/2 c$ towards an open barn with length 
($l_0 = 1m$).

According to a person at rest with the barn, the ladder has a length
$$
\begin{align}
\frac{1}{\gamma} &= \sqrt{1 - \beta^2} \\
\frac{1}{\gamma} &= \sqrt{1 - \frac{3}{4}} \\
\frac{1}{\gamma} &= \sqrt{\frac{1}{4}} \\
\frac{1}{\gamma} &= \frac{1}{2} \\
l &= \frac{l_0}{\gamma} \\
l &= 1m \\
\end{align}
$$
and thus according to the person at rest with the barn the ladder fits within the barn and so they close the doors of the barn to contain it.

According to the person with the ladder this tomfoolery should not work as the barn contracts to $l = 0.5m$ whist the ladder does not contract. This is a supposed contradiction.

We can resolve this with the general Lorentz transform. Letting the un-dashed coordinates be the coordinates in the barn's F.O.R we label the two events:
- Event $0$ is the ladder entering the barn $(t_0, x_0, y_0, z_0) = (0, 0, 0, 0)$
- Event $1$ is the ladder exiting the barn $(t_1, x_1, y_1, z_1) = (0, 1, 0, 0)$

Then we get:
$$
\begin{align}
\gamma &= \frac{1}{\sqrt{1 - \beta^2}}\\
\gamma &= 2\\
t'_0 &= \gamma\left(t_0 - v\frac{x_0}{c^2}\right) \\
&= 2\left(0 - 0\right)\\
&= 0 \\
x_0' &= \gamma \left(x_0 - vt_0\right) \\
&= 2(0 - 0) \\
&= 0 \\
t'_1 &= \gamma\left(t_1 - v\frac{x_1}{c^2}\right) \\
&= 2\left(0 - \frac{\sqrt{3}}{2}1\right)\\
&= -\sqrt 3\\
x_1' &= \gamma \left(x_1 - vt_1\right) \\
&= 2(1 - 0) \\
&= 2 \\
\end{align}
$$
## Velocity transformations
### Addition of velocities
Say we have 3 reference frames: $\mathcal S, \mathcal S', \mathcal S''$ and $\mathcal S''$ is moving with velocity $v_2$ W.R.T $\mathcal S'$ and $\mathcal S'$ is moving with velocity $v_1$ W.R.T $\mathcal S$.

In order to find the velocity of $\mathcal S''$ W.R.T $\mathcal S$ we need to do two Lorentz transforms:
$$
\begin{align}
\pmatrix{ct' \\ x'} &= \gamma_1 \pmatrix{1 & -\beta_1 \\ -\beta_1 & 1} \pmatrix{ct \\ x} \\
\pmatrix{ct'' \\ x''} &= \gamma_2 \pmatrix{1 & -\beta_2 \\ -\beta_2 & 1}\gamma_1 \pmatrix{1 & -\beta_1 \\ -\beta_1 & 1} \pmatrix{ct \\ x} \\
&= \gamma_1 \gamma_2 \pmatrix{1 + \beta_1 \beta_2 & -\beta_1 - \beta_2 \\ -\beta_1 - \beta_2 & 1 + \beta_1\beta_2} \pmatrix{ct \\ x} \\
&= \gamma_1 \gamma_2 [1 + \beta_1\beta_2] \pmatrix{1 & -\frac{\beta_1 + \beta_2}{1 + \beta_1\beta_2} \\ -\frac{\beta_1 + \beta_2}{1 + \beta_1\beta_2} & 1} \pmatrix{ct \\ x} \\
\end{align}
$$
This is just another Lorentz transform where $\gamma = \gamma_1\gamma_2[1 + \beta_1\beta_2]$ and $\beta = \frac{\beta_1 + \beta_2}{1 + \beta_1 \beta_2}$. We can now use $\beta$ to find the velocity of $\mathcal S''$ W.R.T $\mathcal S$:
$$
\begin{align}
\frac{v}{c}&= \beta \\
&= \frac{\beta_1 + \beta_2}{1 + \beta_1 \beta_2} \\
v &= \frac{v_1 + v_2}{1 + \frac{v_1 v_2}{c^2}} \\
\end{align}
$$
Thus adding velocities from two different reference frames looks like applying the above formula.
### Velocity transformations
This is cool but what about transforming velocities between frames of reference? We can use the Lorentz transforms on differentials:
$$
\begin{align}
dt' &= \gamma(dt - V\frac{dx}{c^2}) \\
dx' &= \gamma(dx - Vdt) \\
dy' &= dy \\
dz' &= dz \\
\end{align}
$$
Dividing the left sides by $dt'$ we get
$$
\begin{align}
\frac{dx'}{dt'} &= \frac{\gamma(dx - Vdt)}{\gamma(dt - V\frac{dx}{c^2})} \\
&= \frac{v_x - V}{1 - \frac{Vv_x}{c^2}} \\
\frac{dy'}{dt'} &= \frac{dy}{\gamma(dt - V\frac{dx}{c^2})} \\
&= \frac{v_y}{\gamma(1 - \frac{Vv_x}{c^2})} \\
\frac{dz'}{dt'} &= \frac{dz}{\gamma(dt - V\frac{dx}{c^2})} \\
&= \frac{v_z}{\gamma(1 - \frac{Vv_x}{c^2})} \\
\end{align}
$$
