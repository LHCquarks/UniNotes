## Intutition
Maxwell's equations are linear, differential equations so it is worth looking at some general techniques for these kind of equations.

Say we have the equation
$$
\begin{align}
L[y(x)] = f(x)
\end{align}
$$
where:
- $L$ is a linear differential operator
- $y(x)$ is the function we are solving for
- $f(x)$ is some provided function

In electrostatics a common technique to find our potential was to apply a linear sum over infinite point charges. Green's functions are just like the potential function of a point charge. Once we have the Green's function for the specific operator $L$ we can find our general $y$ by applying a linear summation.
## Derivation
Lets consider the simpler situation where we substitue $\delta(x-\zeta)$ for $f(x)$ thus
$$
\begin{align}
L [G(x;\zeta)] = \delta(x-\zeta)
\end{align}
$$
where $G(x;\zeta)$ is some function that solves this equation. This special function is called Green's function and we will see it can discribe the general case quite well.

Assuming we know this Green's function, we can multiply by $f(\zeta)$ and integrate to get:
$$
\begin{align}
L_x[G(x;\zeta)] &= \delta(x - \zeta) \\
f(\zeta)L_x[G(x;\zeta)] &= f(\zeta)\delta(x - \zeta) \\
\int L_x[f(\zeta)G(x;\zeta)]d\zeta &= \int f(\zeta)\delta(x - \zeta) d\zeta\\
L_x\left[\int f(\zeta)G(x;\zeta)d\zeta\right] &= f(x)\\
\end{align}
$$
Notice that we have reconstructed our original problem with a solution for $y$ with
$$
\begin{align}
y(x) = \int f(\zeta) G(x;\zeta) d\zeta
\end{align}
$$
This is really cool as by just finding $G$ we can find $y$ for any $f$ assuming we can solve the integral.

In a sense this becomes an inverse operator for $L$. 
## Common Green's functions
### Free space electrostatic Green's function
If we wish to solve the equation
$$
\begin{align}
\nabla^2 y(x) = f(x)
\end{align}
$$
for 3d we just have to find the Green's function that solves
$$
\begin{align}
\nabla^2 G(x;\zeta) = \delta(x - \zeta)
\end{align}
$$
Recalling Gauss's law for a stationary point charge (assuming the coulomb guage) we remember
$$
\begin{align}
\nabla^2 \varphi (x; \zeta) &= -\frac{\delta(x - \zeta)}{\epsilon_0} \\
\varphi(x;\zeta) &= \frac{1}{4\pi\epsilon_0} \frac{1}{|x - \zeta|}
\end{align}
$$
thus the free space electrostatic Green's function is
$$
\begin{align}
G(x;\zeta) &= \frac{1}{4\pi} \frac{1}{|x - \zeta|}
\end{align}
$$
### d'Alembert Green's function
We want to solve the equation:
$$
\begin{align}
\Box_w G(\vec r, t; \vec r', t') &= -\delta(\vec r - \vec r') \delta(t - t')
\end{align}
$$
Where $\Box_w$ is the d'Alembertian operator with $\Box_w = \nabla^2 - \frac{1}{c^2}\partial_t^2$.

First we notice that because space is homogeneous and isotropic our greens function can only be concerned with the relative distances between our $\vec r, \vec r'$ and $t, t'$ and thus our function must be of $G(\vec R, \tau)$ where $\vec R = \vec r - \vec r', \tau = t - t'$.

Now, knowing this consider the effects of our $\Box_w$ operator. If we write $\nabla^2$ as the Laplacian acting on the $\vec r$ vector and $\nabla^2_R$ and the laplacian acting on our $\vec R$ vector then:
$$
\begin{align}
\Box_w G &= \nabla^2 G - \frac{1}{c^2}\partial^2_t G \\
&= \nabla^2_R G - \frac{1}{c^2} \partial_\tau^2 G \\
-\delta (\vec r - \vec r') \delta(t - t') &= -\delta(\vec R) \delta(\tau)
\end{align}
$$
We are now going to take the 4-d Fourier transform of both sides so it would be good to define them for a sec:
$$
\begin{align}
\mathcal F\{f(\vec R, \tau)\}(\vec k, \omega) &= \int_{\mathbb{R}^3}\int_{-\infty}^\infty f(\vec R, \tau) e^{i(\tau \omega - \vec k \cdot \vec R)} d\tau d\vec R \\
\mathcal F^{-1}\{f(\vec k, \omega)\}(\vec R, \tau) &= \int_{\mathbb{R}^3}\int_{-\infty}^\infty f(\vec R, \tau) e^{i(\vec k \cdot \vec R - \tau \omega)} \frac{d\tau}{2\pi} \frac{d\vec R}{(2\pi)^3}
\end{align}
$$
Now, taking the 4-d Fourier transform of both sides we get:
$$
\begin{align}
\mathcal F \{\Box_w G\} &= \mathcal F\{-\delta(\vec R) \delta(\tau)\} \\
\left(-k^2  + \frac{\omega^2}{c^2}\right)\widetilde{\!G} &= -e^{i(\vec 0 \cdot \vec k + 0 \omega)} \\
\left(-k^2  + \frac{\omega^2}{c^2}\right)\widetilde{\!G} &= -1\\
\widetilde{\!G} &= \frac{1}{k^2 - \omega^2 / c^2}\\
\end{align}
$$
Now we need to move back into real space but this will pose some issues. The first step is to apply the time FT:
$$
\begin{align}
I(\tau) &= \frac{1}{2\pi} \int_{-\infty}^\infty \frac{e^{-i \omega \tau}}{k^2 - \omega^2 / c^2} d\tau
\end{align}
$$
#### Finding $I(\tau)$
Now, the intergrand blows up and thus is not integrable so we are going to have to pull off some physics BS re-normalization :). To do this we will define the new contour integral
$$
\begin{align}
J(\tau, \vec k) &= \int_\Omega\frac{e^{-i \tau z}}{k^2 - (z + i \eta)^2 / c^2} dz \\
 &= \int_\Omega\frac{c^2e^{-i \tau z}}{c^2k^2 - (z + i \eta)^2} dz \\
 &= \int_\Omega\frac{c^2e^{-i \tau z}}{(ck - z - i\eta)(c k + z + i\eta)} dz
\end{align}
$$
where $\Omega$ is the semi-circle on the bottom half plane with radius $R > |k + i\eta|$.
Call the intergrand $f(z)$, then the poles of $f(z)$ are at $z = ck - i\eta, -ck - i\eta$ as shown in the diagram:
![[Pasted image 20261025123611.png|362]]
Now, by the residue theorem we have:
$$
\begin{align}
J(\tau, \vec k) &= 2\pi i \left[\text{Res}(f, ck - i \eta) + \text{Res}(f, -ck - i \eta)\right] \\
\end{align}
$$
Calculating these residues gives:
$$
\begin{align}
\text{Res}(f, ck-i\eta) &= \frac{c^2e^{-i\tau (ck - i\eta)}}{(ck + (ck - i\eta) + i\eta)} \\
&= \frac{c^2e^{\eta \tau}e^{-i\tau c k}}{2ck} \\
&= \frac{ce^{\eta \tau}e^{-i\tau c k}}{2k} \\
\text{Res}(f, -ck-i\eta) &= \frac{c^2e^{-i\tau (-ck - i\eta)}}{(ck -(-ck - i\eta) - i\eta)} \\
&= \frac{c^2e^{\eta \tau}e^{i\tau c k}}{2ck} \\
&= \frac{ce^{\eta \tau}e^{i\tau c k}}{2k} \\
\end{align}
$$
And thus:
$$
\begin{align}
J(\tau, \vec k) &= 2\pi i \left[\frac{ce^{\eta \tau}e^{i\tau ck}}{2k} + \frac{ce^{\eta \tau}e^{-i\tau ck}}{2k}\right] \\
&= \frac{c\pi i}{k}e^{\eta \tau}2\cos(\tau ck)  \\
&= \frac{2c\pi i}{k}e^{\eta \tau}\cos(\tau ck) 
\end{align}
$$
Now, we also know that $J(\tau, \vec k) = \int_{\Omega_1}f(z)dz + \int_{\Omega_2}f(z)dz$ but along $\Omega_2$:
$$
\begin{align}
|f(z)| &= \frac{c^2|e^{-i\tau z}|}{|(ck - z - i\eta)(c k + z + i\eta)|} \\
&= \frac{c^2|e^{-\tau\text{Im}(z)}|}{|ck - z - i\eta||c k + z + i\eta|} \\
\end{align}
$$
If we take $\tau < 0$ then we have:
$$
\begin{align}
|f(z)| &\le \frac{e^0}{|z - (ck - i\eta)|\cdot|z - (-ck - i\eta)|} \\
&\le \frac{1}{||z| - |ck - i\eta||\cdot ||z| - |-ck - i\eta||} \\
&\le \frac{1}{|R - |ck - i\eta||\cdot|R - |ck + i\eta||} \\
\end{align}
$$
By the ML-lemma we know that:
$$
\begin{align}
\left |\int_{\Omega_2}f(z) dz\right| &\le \text{max}(|f(z)|) L \\
&\le \frac{1}{|R - |ck - i\eta||\cdot|R - |ck + i\eta||} \pi R\\
&\le \frac{1}{\left|1 - \frac{|ck - i\eta|}{R}\right|\cdot|R - |ck + i\eta||}\\
\end{align}
$$
As $R \rightarrow \infty$ we thus have that:
$$
\begin{align}
\lim_{R \rightarrow \infty}\left |\int_{\Omega_2}f(z) dz\right| &\le \lim_{R \rightarrow \infty} \frac{1}{\left|1 - \frac{|ck - i\eta|}{R}\right|\cdot|R - |ck + i\eta||}\\
&\le \frac{1}{|1 - 0| \cdot |\infty - |ck + i \eta||} \\
&\le \frac{1}{\infty} \\
&\le 0 \\

\end{align}
$$
And thus the contribution of $\Omega_2$ vanishes finally allowing us to conclude that
$$
\begin{align}
\int_{-\infty}^\infty \frac{e^{-i\tau \omega}}{k^2 - (\omega + i\eta)^2/c^2} d\omega &= \frac{2c\pi i}{k}e^{\eta \tau}\cos(\tau ck) 
\end{align}
$$
And taking $\eta \rightarrow 0$ we can conclude that:
$$
\begin{align}
I(\tau) &= \frac{2c\pi i}{k} \cos (\tau c k)
\end{align}
$$
<% tp.file.cursor(2) %>



## Boundary conditions
Due to $G$ being a building block of the scalar field $\varphi$ we inherit the ambiguity of gauges an so boundary conditions can help us take that ambiguity away.

A general solution to $L[y] = f$ involves both a particular solution and all the homogeneous solutions thus a more general form for $\varphi$ with a particular Green's function $G_0$ and a homogeneous solution $\varphi_{\text{hom}}$ is:
$$
\begin{align}
\varphi(x) &= \int f(\zeta)G_0(x, \zeta)d\zeta + \varphi_{\text{hom}}(x)
\end{align}
$$
### Boundary conditions on the Poisson equation
Lets solve $\nabla^2 \varphi = -\frac{\rho}{\epsilon_0}$. We will assume we have a Green's function $G$ (the free space electrostatic function will do).

First we will derive Green's first and second identities for general scalar fields $\phi, \psi$ (not dirrectly related to green's functions):
$$
\begin{align}
\nabla \cdot (\phi \nabla \psi) &= \nabla \phi \cdot \nabla \psi + \phi \nabla^2 \psi \\
\int_V [\nabla \phi \cdot \nabla \psi + \phi \nabla ^2 \psi] dV &= \int_V \nabla \cdot (\phi \nabla \psi) dV \\
\int_V [\nabla \phi \cdot \nabla \psi + \phi \nabla ^2 \psi] dV &= \int_{\partial V} \phi \nabla \psi \cdot  dA \tag {1}\\ 
\end{align}
$$
then interchanging $\phi$ and $\psi$ and subtracting we get:
$$
\begin{align}
\int_V [\nabla \phi \cdot \nabla \psi - \nabla \psi \cdot \nabla \phi + \phi \nabla ^2 \psi - \psi \nabla ^2 \phi] dV &= \int_{\partial V} [\phi \nabla \psi - \psi \nabla \phi]\cdot  dA \\ 
\int_V [\phi \nabla ^2 \psi - \psi \nabla ^2 \phi] dV &= \int_{\partial V} [\phi \nabla \psi - \psi \nabla \phi]\cdot  dA \tag{2}\\ 
\end{align}
$$
Substituting $\phi = \varphi(r'), \psi = G(r', r)$ we then get the identity:
$$
\begin{align}
\int_V [\varphi(r') (\nabla^2)' G(r'; r) - G(r';r) (\nabla^2)' \varphi(r')]dV' &= \int_{\partial V} [\varphi(r') \nabla' G(r';r) - G(r';r)\nabla' \varphi(r')]\cdot dA' \\
\int_V \left[\varphi(r') \delta(r' - r) + G(r';r) \frac{\rho(r')}{\epsilon_0}\right]dV' &= \int_{\partial V} [\varphi(r') \nabla' G(r'; r) - G(r'; r)\nabla' \varphi(r')]\cdot dA' \\
\varphi(r) + \int_V G(r';r) \frac{\rho(r')}{\epsilon_0}dV' &= \int_{\partial V} [\varphi(r') \nabla' G(r'; r) - G(r'; r)\nabla' \varphi(r')]\cdot dA' \\
\varphi(r) &=  -\frac{1}{\epsilon_0}\int_V G(r';r) \rho(r')dV'  \\
&+\int_{\partial V} \varphi(r') \nabla' G(r'; r)\cdot dA' \\
&-\int_{\partial V} G(r'; r)\nabla' \varphi(r')\cdot dA' \\
\end{align}
$$
These terms have fairly easy to see meanings:
- The first term is the what we expect from Laplace's equation
- The second term is a correcting term for the potential on the boundary
- The third term is a correcting term for the normal of the potential.
#### Example
Say we have a conducting spherical shell set to $\varphi = V_0$ centered on the origin with no internal charge distribution. Then:
$$
\begin{align}
\varphi (r) &= -\frac{1}{\epsilon_0} \int_V G(r';r)(0) dV' + \int_{\partial V} (V_0) \nabla'G(r';r) \cdot dA' - \int_{\partial V} G(r';r) \nabla' (V_0) \cdot dA' \\
\varphi (r) &= \int_{\partial V} V_0 \nabla'G(r';r) \cdot dA'  -\int_{\partial V} G(r';r) \vec 0 \cdot dA' \\
\varphi (r) &= \int_{\partial V} V_0 \nabla'G(r';r) \cdot dA'  \\
\end{align}
$$
We can notice that setting $V_0 = 0$ makes our problem trivial but by gauge symmetry $\varphi + V_0$ produces the same electric field as $\varphi$ and will therefore will solve the boundary conditions. This means that:
$$
\begin{align}
\varphi_0(r) &= \int_{\partial V} (0) \nabla' G(r';r) \cdot A' \\
&= 0 \\
\varphi (r) &= \varphi_0(r) + V_0 \\
&= V_0
\end{align}
$$
Hence inside the sphere $\varphi$ is constant which produces an electric field of $\vec E = 0$ which aligns with what we expect from Guass's law.