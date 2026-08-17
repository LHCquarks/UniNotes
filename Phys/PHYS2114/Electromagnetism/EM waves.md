---
aliases:
---
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
### Partially polarized light
A crucial assumption we made was $\vec E_0$  was independent of time. If however $\vec E_0$ changes slowly throughout time we get our new electric field as
$$
\begin{align}
\vec E &= \vec E_0(t) e^{-i\omega t}
\end{align}
$$
### Polarization density matrix
Polarization behaves identically to entangled spin in quantum mechanics so we will take a leaf out of their book and construct a spin density matrix.

Essentially we will construct a matrix with each entry $P_{\alpha, \beta}$ describing the probability that the light is found in a polarization of $\alpha,\beta$. This is done through the time average and normalizing (letting the trace be $1$):
$$
\begin{align}
P &= \frac{1}{\overline{E_{0,y}E_{0, y}^*} + \overline{E_{0,z} E_{0, z}^*}}\pmatrix{
\overline{E_{0,y}E_{0, y}^*} & \overline{E_{0,y} E_{0, z}^*} \\
\overline{E_{0,z}E_{0, y}^*} & \overline{E_{0,z} E_{0, z}^*}
} \\
&= \frac{1}{|E_{0,y}|^2 + |E_{0,z}|^2}\pmatrix{
\overline{E_{0,y}E_{0, y}^*} & \overline{E_{0,y} E_{0, z}^*} \\
\overline{E_{0,z}E_{0, y}^*} & \overline{E_{0,z} E_{0, z}^*}
} \\
\end{align}
$$
It goes without saying but this is a Hermitian matrix.

For fully polarized light $E_0$ is time independent so the determinate of our polarization density matrix is
$$
\begin{align}
|P| &= E_{0, y}E_{0, y}^*E_{0, z}E_{0, z}^* - E_{0, y}E_{0, z}^* E_{0, z}E_{0, y}^* \\
&= 0
\end{align}
$$
For fully polarized light it is equally likely for it to be in the $y$-direction as in the $z$-direction and so our PDM becomes
$$
\begin{align}
P &= \frac{1}{2}\pmatrix{1 & 0 \\ 0 & 1} \\
|P| &= \frac{1}{4}

\end{align}
$$

We can then numerically define the **degree of polarization** ($p$) of our wave with
$$
\begin{align}
|P| &= \frac{1}{4} ( 1 - p^2)
\end{align}
$$
### Stoke's parameters
Because the matrix is hermitian and the trace adds to 1 we only need 3 real numbers to fully parameterize the matrix. These parameters are called **stoke's parameters** and are:
$$
\begin{align}
P &= \frac{1}{2}\pmatrix{1 + \zeta_3 & \zeta_1 - i\zeta_2 \\ \zeta_1 + i \zeta_2 & 1 - \zeta_3 }
\end{align}
$$
The determinate of this matrix is then
$$
\begin{align}
|P| &= \frac{1}{4}(1 - \zeta_1^2 - \zeta_2^2 - \zeta_3^2)
\end{align}
$$
Hence $p = \sqrt{\zeta_1^2 + \zeta_2^2 + \zeta_3^2}$ 
## Refractance and transmisiantce
Consider 2 media with refractive indices of $n_1$ and $n_2$ respectively and incident a wave with a fixed frequency at an angle $\theta_i$ as in the diagram below
![[Pasted image 20260817095743.png]]
Also consider time $t=0$ thus our equations for our light waves become
$$
\begin{align}
\vec E_i &= \vec E_{0, i}e^{i\vec k_i \cdot \vec r} \\
\vec E_r &= \vec E_{0, r}e^{i\vec k_r \cdot \vec r} \\
\vec E_t &= \vec E_{0, t}e^{i\vec k_t \cdot \vec r} \\
\end{align}
$$
Taking $k$ to be the magnitude of the $\vec k$ vector in a vacuum we get expressions for our $k$ values as such:
$$
\begin{align}
\vec k_i &= n_1k(\cos \theta_i \hat x + \sin\theta_i \hat y) \\
\vec k_r &= n_1k(-\cos\theta_r \hat x + \sin\theta_r \hat y) \\
\vec k_t &= n_2k(\cos \theta_t \hat x + \sin\theta_t \hat y)
\end{align}
$$
Dotting with $\vec r$  and evaluating at $x = 0$ we get the expressions
$$
\begin{align}
\vec k_i \cdot \vec r &= n_1ky\sin\theta_i \\
\vec k_r \cdot \vec r &= n_1ky\sin\theta_r \\
\vec k_r \cdot \vec r &= n_2ky\sin\theta_t
\end{align}
$$
then using Snell's law and noting that $\theta_i = \theta_r$ we get that for all $\vec k_\alpha$ we have that $\vec k_\alpha \cdot \vec r = n_1ky\sin\theta_i$.
### Transverse Electric field
In this scenario the electric field is transverse to the plane in which our incident ray lies and thus points purely in the $z$-direction. This is also commonly referred to the $s$ component. In this case we let $E_{0,i} = \hat z$  and thus we get
$$
\begin{align}
E_i &= e^{i \vec k_i \cdot \vec r} \hat z \\
E_r &= r_se^{i \vec k_r \cdot \vec r} \hat z\\
E_t &= t_se^{i \vec k_t \cdot \vec r} \hat z\\
\end{align}
$$
Assuming that the electric and magnetic fields are continuous and doing a bit of geometry we get that
![[Pasted image 20260817112409.png]]
$$
\begin{align}
E_i + E_r &= E_t \tag{1}\\
B_i\sin\theta_i + B_r\sin \theta_r &= B_t\sin\theta_t \tag{2}\\
-B_i\cos\theta_i + B_r\cos \theta_r &= -B_t\cos \theta_t \tag {3}
\end{align}
$$
applying $B = \frac{n}{c}E$ and substituting in our expression for $E$ we get
$$
\begin{align}
e^{i \vec k_i \cdot \vec r} + r_s e^{i \vec k_r \cdot \vec r} &= t_s e^{i\vec k_t \cdot \vec r} \tag{1} \\
\implies 1 + r_s &= t_s \\
\frac{n_1}{c}\sin\theta_ie^{i\vec k_i\cdot \vec r} + \frac{n_1}{c}\sin\theta_rr_se^{i\vec k_r \cdot \vec r} &= \frac{n_2}{c}\sin\theta_t t_se^{i\vec k_t\cdot \vec r} \tag{2} \\
\implies n_1 \sin\theta_i + n_1r_s\sin\theta_r &= n_2 t_s\sin \theta_t \\
n_1 \sin\theta_i (1 + r_s) &= n_2 t_s\sin \theta_t \\
n_1 \sin\theta_i &= n_2 \sin \theta_t \\
-\frac{n_1}{c}\cos\theta_ie^{i\vec k_i\cdot \vec r} + \frac{n_1}{c}\cos\theta_rr_se^{i\vec k_r \cdot \vec r} &= -\frac{n_2}{c}\cos\theta_t t_se^{i\vec k_t\cdot \vec r} \tag{3} \\
\implies n_1\cos\theta_i - n_1\cos\theta_rr_s &= n_2\cos\theta_t t_s \\
n_1\cos\theta_i &= n_2\cos\theta_t (1 + r_s) + n_1\cos\theta_rr_s\\
n_1\cos\theta_i - n_2\cos\theta_t &= r_s(n_2\cos\theta_t + n_1\cos\theta_r)\\
r_s &= \frac{n_1 \cos \theta_i - n_2 \cos \theta_t}{n_2\cos\theta_t + n_1 \cos\theta_r} \\
r_s &= \frac{n_1 \cos \theta_i - n_2 \cos \theta_t}{n_1 \cos\theta_i + n_2\cos\theta_t} \\
t_s &= \frac{2n_1 \cos \theta_i}{n_1 \cos\theta_i + n_2\cos\theta_t}
\end{align}
$$
The expression we derived in $(2)$ is just Snell's law and with $(3)$ we derived the Fresnel equations for the transverse electric field.
