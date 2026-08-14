## From Maxwell's equations
Consider free space where $\rho = 0, \vec J = 0$ and take the two curl Maxwell equations:
$$
\begin{align}
\vec \nabla \times \vec E + \frac{\partial \vec B}{\partial t} &= 0 \tag {1}\\
\vec \nabla \times \vec B - \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t} &= 0 \tag{2} \\
\end{align}
$$
Now, taking the curl of equ $(1)$ we get: 
$$
\begin{align}
\vec \nabla \times \left(\vec \nabla \times \vec E + \frac{\partial \vec B}{\partial t}\right) &= \vec \nabla \times 0 \\
\vec \nabla (\vec \nabla \cdot \vec E) - \vec \nabla^2 \vec E + \frac{\partial}{\partial t}(\vec \nabla \times \vec B) &= 0 \\
\vec \nabla (0) - \vec \nabla^2 \vec E + \frac{\partial}{\partial t}\left(\mu_0\epsilon_0\frac{\partial \vec E}{\partial t}\right) &= 0 \\
\left(\mu_0\epsilon_0 \partial ^2_t-\vec \nabla^2\right) \vec E &= 0
\end{align}
$$
We can do a similar thing with equ $(2)$ to get:
$$
\begin{align}
\vec \nabla \times \left(\vec \nabla \times \vec B - \mu_0\epsilon_0 \frac{\partial \vec E}{\partial t}\right) &= 0 \\ 
-\nabla^2 \vec B - \mu_0\epsilon_0 \frac{\partial }{\partial t}\left(\vec \nabla \times \vec E\right) &= 0\\
\left(\mu_0\epsilon_0\partial^2_t - \nabla^2\right)\vec B &= 0
\end{align}
$$
These two equations are wave equations. Assuming that our wave propagates only in the $x$-direction $(E_x = B_x = 0)$ then our two equations simply become
$$
\begin{align}
\left(\mu_0\epsilon_0\partial^2_t - \partial^2_x\right)E_{y, z} &= 0 \\
\left(\mu_0\epsilon_0\partial^2_t - \partial^2_x\right)B_{y, z} &= 0
\end{align}
$$
These equations have the solution $f(x, t) = f_-(x - ct) + f_+(x + ct)$ for arbitrary functions $f_-$ and $f_+$ and with $c = \frac{1}{\sqrt{\mu_0\epsilon_0}}$.

The solution for $f_-$ represents the wave moving to the right whilst $f_+$ represents the wave moving to the left.
