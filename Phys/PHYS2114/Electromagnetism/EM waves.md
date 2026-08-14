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
Thus for each Cartesian component of $\vec E$ and $\vec B$ we get the differential equation
$$
\begin{align}
\mu_0\epsilon_0\frac{\partial^2 f}{\partial t^2} - \frac{\partial^2 f}{\partial x^2} &= 0 \\
\end{align}
$$
This is just the wave equation and has the known solutions $f(x, t) = f_-(x-ct) + f_+(x + ct)$ where $c = \frac{1}{\sqrt{\mu_0\epsilon_0}}$ and $f_-, f_+$ are arbitrary functions. Here $f_-$ propagates from left to right whist $f_+$ propagates from right to left.

## Plane wave solution
Consider a wave that only depends on $x$ and $t$. In this case we find that 
$$
\begin{align}
\mu_0\epsilon_0 \frac{\partial^2 E_x}{\partial t^2} - \frac{\partial^2E_x}{\partial x^2} &= 0 \\
E_x(x, t) &= E_{x, -}(x - ct) + E_{x, +}(x + ct) \\
\mu_0\epsilon_0 \frac{\partial^2 E_y}{\partial t^2} - \frac{\partial^2E_y}{\partial y^2} &= 0 \\
\mu_0\epsilon_0 \frac{\partial^2 E_y}{\partial t^2} &= 0 \\
E_y(x, t) &= E_{y, 1}(x)t + E_{y, 2}(x) \\
\mu_0\epsilon_0 \frac{\partial^2 E_z}{\partial t^2} - \frac{\partial^2E_z}{\partial z^2} &= 0 \\
\mu_0\epsilon_0 \frac{\partial^2 E_z}{\partial t^2} &= 0 \\
E_z(x, t) &= E_{z, 1}(x)t + E_{z, 2}(x) \\
\mu_0\epsilon_0 \frac{\partial^2 B_x}{\partial t^2} - \frac{\partial^2B_x}{\partial x^2} &= 0 \\
B_x(x, t) &= B_{x, -}(x - ct) + B_{x, +}(x + ct) \\
\mu_0\epsilon_0 \frac{\partial^2 B_y}{\partial t^2} - \frac{\partial^2B_y}{\partial y^2} &= 0 \\
\mu_0\epsilon_0 \frac{\partial^2 B_y}{\partial t^2} &= 0 \\
B_y(x, t) &= B_{y, 1}(x)t + B_{y, 2}(x) \\
\mu_0\epsilon_0 \frac{\partial^2 B_z}{\partial t^2} - \frac{\partial^2B_z}{\partial z^2} &= 0 \\
\mu_0\epsilon_0 \frac{\partial^2 B_z}{\partial t^2} &= 0 \\
B_z(x, t) &= B_{z, 1}(x)t + B_{z, 2}(x) \\

\end{align}
$$


We will now assume that our wave propagates in the $x$-direction meaning $\vec S \parallel \hat x$  and thus $\vec E, \vec B \perp \hat x$ so $E_x = B_x = 0$. We can also align our coordinate system so that 


These two equations are wave equations. Assuming that our wave propagates only in the $x$-direction $(E_x = B_x = 0)$.
