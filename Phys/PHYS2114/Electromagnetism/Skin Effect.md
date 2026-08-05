Consider a wire carrying AC current. We want to find out where in the conductor the charge is flowing.

Because we are considering a metal we get $\epsilon \approx 1$ and we will assume it has no magnetic properties so $\mu \approx 1$.

There are no net charges present ($\rho = 0$) and when we consider low frequencies ($l \ll \lambda = \frac{c}{f}$) we get that $\epsilon_0 \frac{\partial \vec E}{\partial t} \ll \vec J$ and so we can ignore it thus our Maxwell equations become:
$$
\begin{align}
\vec \nabla \cdot \vec E &= 0 \\
\vec \nabla \cdot \vec B &= 0 \\
\vec \nabla \times \vec E &= -\frac{\partial \vec B}{\partial t} \\
\vec \nabla \times \vec B &= \mu_0 \vec J
\end{align}
$$
Further, Ohm's law states that 
$$
\begin{align}
\vec J &= \sigma \vec E
\end{align}
$$
To eliminate for $\vec B$ we substitute Ohm's law into the last Maxwell equation and take the curl of both sides like so:
$$
\begin{align}
\vec \nabla \times \vec B &= \mu_0 \vec J \\
\vec \nabla \times \vec B &= \mu_0 \sigma \vec E \\
\vec \nabla \times \left(\vec \nabla \times \vec B\right) &= \mu_0 \sigma \left(\vec \nabla \times \vec E \right)\\
\nabla\left(\vec \nabla \cdot \vec B\right)- \nabla^2 \vec B &= -\mu_0 \sigma \frac{\partial \vec B}{\partial t} \\
\nabla (0)- \nabla^2 \vec B &= -\mu_0 \sigma \frac{\partial \vec B}{\partial t} \\
\nabla^2 \vec B &= \mu_0 \sigma \frac{\partial \vec B}{\partial t} \\
\end{align}
$$
Because the current is AC we expect the magnetic field to vary harmonically with time ($\vec B = \vec b e^{-i\omega t}$)  and so we will pug in our ansatz to get
$$
\begin{align}
\nabla^2 \vec b e^{-i\omega t} &= -i\omega\mu_0 \sigma \vec b e^{-i \omega t} \\
\nabla^2 \vec b &= -i\omega\mu_0\sigma\vec b
\end{align}
$$
We will now consider the simple geometry defined by a half plane of metal $z > 0$ and assume the current flows in the $x$-direction
![[Pasted image 20260805132457.png]]
Because $\vec B$ can not depend on x or y due to symmetry and our right hand rule states that $\vec B$ is in the $y$-dirrection our equation becomes
$$
\begin{align}
\pmatrix{0\ \  \\ \partial^2_z b_y \\ 0\ \ } &= -i\omega\mu_0\sigma \vec b \\
\end{align}
$$
Thus $(\vec b)_x = (\vec b)_y = 0$  whist $(\vec b)_z$ follows the equation
$$
\begin{align}
\partial^2_z b_y &= -i\omega\mu_0\sigma b_y \\
\end{align}
$$
This invites us to make another ansatz $b_y = B_0e^{\lambda z}$ were we find:
$$
\begin{align}
\lambda^2 &= -i\omega \mu_0\sigma \\
\lambda &= \pm\sqrt{-i} \sqrt{\omega\mu_0\sigma} \\
&= \pm(1- i) \sqrt{\frac{\omega\mu_0\sigma}{2}}
\end{align}
$$
Obviously we can not have $\vec B$ blow up to infinity as $z \rightarrow \infty$ thus we have to throw away the positive solution. Further, we can sum up all the coefficients into one variable $\delta = \sqrt{\frac{2}{\omega\mu_0\sigma}} = \sqrt{\frac{2\rho}{\omega\mu_0}}$ and thus our solution becomes:
$$
\begin{align}
\vec B &= B_0e^{-z/\delta} e^{i(z/\delta - \omega t)}\hat \jmath
\end{align}
$$
of course only the real part of this is the magnetic field and so 
$$
\begin{align}
\vec B(z, t) &= B_0 e^{-z/\delta}\cos(z/\delta - \omega t)\hat \jmath
\end{align}
$$
From here it is really easy to find both $\vec J$ and $\vec E$:

For $\vec J$ we use that $\vec \nabla \times \vec B = \mu_0\vec J$ and thus
$$
\begin{align}
\mu_0\vec J &= -\partial_zB_y \hat \imath\\
&= -B_0\left[-\frac{1}{\delta}e^{-z/\delta}e^{i(z/\delta-\omega t)} + \frac{i}{\delta}e^{z / \delta} e^{i(z / \delta - \omega t)}\right] \\
&= \frac{B_0}{\delta}(1 - i)e^{-z/\delta}e^{i(z/\delta-\omega t)}\\
\vec J&= \frac{\sqrt{2}B_0}{\mu_0\delta}e^{-i\pi/4}e^{-z/\delta}e^{i(z/\delta-\omega t)}\\
\vec J&= \frac{\sqrt{2}B_0}{\mu_0\delta}e^{-z/\delta}\cos(z/\delta - \omega t - \pi / 4)\\
\end{align}
$$
