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
## Plane wave solution
If we assume that our wave only depends on $x$ our equations simplify and for each Cartesian component of $\vec E$ and $\vec B$ we get the differential equation
$$
\begin{align}
\mu_0\epsilon_0\frac{\partial^2 f}{\partial t^2} - \frac{\partial^2 f}{\partial x^2} &= 0 \\
\end{align}
$$
This is just the wave equation and has the known solutions $f(x, t) = f_-(x-ct) + f_+(x + ct)$ where $c = \frac{1}{\sqrt{\mu_0\epsilon_0}}$ and $f_-, f_+$ are arbitrary functions. Here $f_-$ propagates from left to right whist $f_+$ propagates from right to left.

Because our wave is moving only in the $x$-direction it is safe to assume the energy transfer also only happens in the $x$-direction meaning $\vec S \parallel \hat x$. Because $\vec S = \frac{1}{\mu_0}\left[\vec E \times \vec B\right]$ we can conclude that $\vec E, \vec B \perp \hat x$ and thus has no $x$-component. Thus we have the equations
$$
\begin{align}
E_x &= 0 \\
E_y &= E_{y, -}(x - ct) + E_{y, +}(x + ct) \\
E_z &= E_{z, -}(x - ct) + E_{z, +}(x + ct) \\
B_x &= 0 \\
B_y &= B_{y, -}(x - ct) + B_{y, +}(x + ct) \\
B_z &= B_{z, -}(x - ct) + B_{z, +}(x + ct) \\
\end{align}
$$
We will now start working with our potentials and so it will be good to select our gauges
### Gauge aside
In this scenario it is suitable to assume both the Lorentz gauge and the Coulomb gauge
and thus we have the constraints
$$
\begin{align}
\vec \nabla \cdot \vec A + \mu_0\epsilon_0\partial_t\varphi &= 0 \tag{1}\\
\vec \nabla \cdot \vec A &= 0 \tag{2} \\
\end{align}
$$
Applying $(2)$ to $(1)$ we get
$$
\begin{align}
\mu_0 \epsilon_0 \partial_t \varphi &= 0 \\
\varphi &= C
\end{align}
$$
Relating our potentials back to our fields we have 
$$
\begin{align}
\vec B &= \vec \nabla \times \vec A \\
\vec E &= -\nabla \varphi - \frac{\partial \vec A}{\partial t} \\
&= 0- \frac{\partial \vec A}{\partial t} \\
\vec E &= - \frac{\partial \vec A}{\partial t} \\
\end{align}
$$
<% tp.file.cursor(2) %>