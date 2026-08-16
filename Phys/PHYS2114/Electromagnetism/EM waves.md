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
### Plane wave solution
If we assume that our wave only depends on $x$ our equations simplify and for each Cartesian component of $\vec E$ and $\vec B$ we get the differential equation
$$
\begin{align}
\mu_0\epsilon_0\frac{\partial^2 f}{\partial t^2} - \frac{\partial^2 f}{\partial x^2} &= 0 \\
\end{align}
$$
This is just the wave equation and has the known solutions $f(x, t) = f_-(x-ct) + f_+(x + ct)$ where $c = \frac{1}{\sqrt{\mu_0\epsilon_0}}$ and $f_-, f_+$ are arbitrary functions. Here $f_-$ propagates from left to right whist $f_+$ propagates from right to left.

We will further assume that our wave only propagates in the positive $x$-direction ($f_+(\zeta) = 0$).
Because our wave is moving only in the $x$-direction it is safe to assume the energy transfer also only happens in the $x$-direction meaning $\vec S \parallel \hat x$. Because $\vec S = \frac{1}{\mu_0}\left[\vec E \times \vec B\right]$ we can conclude that $\vec E, \vec B \perp \hat x$ and thus has no $x$-component. Thus we have the equations
$$
\begin{align}
E_x &= 0 \\
E_y &= E_y(x - ct) \\
E_z &= E_z(x - ct) \\
B_x &= 0 \\
B_y &= B_y(x - ct) \\
B_z &= B_z(x - ct) \\
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
### Finding the potential
We can now use the electric field to find the vector potential:
$$
\begin{align}
E_x &= -\frac{\partial A_x}{\partial t} \\
A_x &= C_x \\
E_y &= -\frac{\partial A_y}{\partial t} \\
\int E_y(x - ct)dt &= -A_y(x, t)\\
\zeta &=x - ct \\
A_y(x, t) &= c\int E_y(\zeta)d\zeta \\
A_z(x, t) &= c\int E_z(\zeta)d\zeta
\end{align}
$$
Redefining $\vec E$  in terms of $\vec A(x, t)$ we get
$$
\begin{align}
\vec E &= \left(0, c\frac{dA_y}{d\zeta}, c\frac{dA_z}{d\zeta}\right)
\end{align}
$$
with
$$
\begin{align}
A_y(x, t) &= A_y(\zeta) \\
&= A_y(x - ct)
\end{align}
$$
We can then take the curl of $A$ to obtain
$$
\begin{align}
\vec B &= \vec \nabla \times \vec A \\
&= \left(\partial_yA_z - \partial zA_y, \partial_z A_x - \partial_xA_z, \partial_x A_y - \partial_y A_x\right) \\
&= \left(0 - 0, 0 - \partial_xA_z, \partial_x A_y - 0\right) \\
&= \left(0, - \frac{d A_z}{d\zeta}\frac{\partial \zeta}{\partial x}, \frac{d A_y}{d\zeta}\frac{\partial \zeta}{\partial x}\right) \\
&= \left(0, - \frac{d A_z}{d\zeta}, \frac{d A_y}{d\zeta}\right) \\

\end{align}
$$
Taking $\vec E \cdot \vec B$ we get
$$
\begin{align}
\vec E \cdot \vec B &= -c\frac{dA_y}{d\zeta}\frac{dA_z}{d\zeta} + c\frac{dA_z}{d\zeta}\frac{dA_y}{d\zeta} \\
&= 0
\end{align}
$$
so $\vec E$ and $\vec B$ are always perpendicular to each other and the direction of motion. In-fact we can say more, if $\hat n$ is the direction of propagation we hat that
$$
\begin{align}
\vec B &= \frac{1}{c} \left[\hat n \times \vec E\right]
\end{align}
$$
Which we can then substitute into the poynting vector to get
$$
\begin{align}
\vec S &= \frac{1}{\mu_0c}\left[\vec E\times \left[\hat n \times \vec E\right]\right] \\
\vec S &= \frac{1}{\mu_0c}E^2 \hat n
\end{align}
$$

## Monochromatic light
Monochromatic light only has one frequency hence
$$
\begin{align}
\vec E \propto e^{-i\omega t}
\end{align}
$$
We know that $\vec E$ is a function of $x - ct$ hence $\vec E$ must be given by
$$
\begin{align}
\vec E &= \vec E_0 e^{ikx - i\omega t}
\end{align}
$$
where $\omega = c k$ and $k$ is called the wave number and $\vec E_0$ is some real vector encoding the initial state of the wave. From just the electric field we can get both the vector potential and then the magnetic field so $\vec E$ is sufficient to describe the entire wave.
## Polarization
### $b$ vector representation
Whist this $\vec E_0$ representation is good and all we can find a more enlightening way of putting it.

Because $\vec E_0$ is an arbitrary complex vector $E_0^2 = E_{0, x}^2 + E_{0, y}^2 + E_{0, z}^2$ is an arbitrary complex number and so we can re-write it as
$$
\begin{align}
E_0^2 &= |E_0^2| e^{-2i\alpha}
\end{align}
$$
For some angle alpha and thus there is some complex vector $\vec b$ such that $b^2 \in \mathbb R$ and 
$$
\begin{align}
\vec E_0 &= \vec b e^{-i\alpha}
\end{align}
$$
Further, we can write this complex vector as $\vec b = \vec b_1 + i\vec b_2$ where $\vec b_1, \vec b_2 \in \mathbb R^3$ and we get
$$
\begin{align}
b^2 &= b_1^2 - b_2^2 + 2i\vec b_1 \cdot \vec b_2
\end{align}
$$
which because $b^2 \in \mathbb R$ implies that $\vec b_1 \perp \vec b_2$.


Letting our EM wave travel along the $x$-axis and assuming that $\vec b_1$ is along the $y$-axis we can write our EM wave as:
$$
\begin{align}
E_y &= b_1 \cos (\omega t - kx + \alpha) \\
E_z &= \pm b_2 \sin(\omega t - kx + \alpha)
\end{align}
$$
and hence our electric field obeys the relationship 
$$
\begin{align}
\frac{E_y^2}{b_1^2} + \frac{E_z^2}{b_2^2} &= 1
\end{align}
$$
the equation for an ellipse. This is called **elliptically polarized light**.
### probability density matrix
### stoke's parameters
