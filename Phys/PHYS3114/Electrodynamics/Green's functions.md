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
## Boundary conditions
Due to $G$ being a building block of the scalar field $\varphi$ we inherit the ambiguity of gauges an so boundary conditions can help us take that ambiguity away.

A general solution to $L[y] = f$ involves both a particular solution and all the homogenous solutions thus a more general form for $\varphi$ with a particular Green's funciton $G_0$ and a homogenous solution $\varphi_{\text{hom}}$ is:
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
- The first term is the what we expect from Laplace's eqation
- The second term is a correcting term for the potential on the boundary
- The third term is a correcting term for the normal of the potential.
#### Example
Say we have a conducting spherical shell set to $\varphi = V_0$ centered on the origin with no internal charge distrobution. Then:
$$
\begin{align}
\varphi (r) &= -\frac{1}{\epsilon_0} \int_V G(r';r)(0) dV' + \int_{\partial V} (V_0) \nabla'G(r';r) \cdot dA' - \int_{\partial V} G(r';r) \nabla' (V_0) \cdot dA' \\
\varphi (r) &= \int_{\partial V} V_0 \nabla'G(r';r) \cdot dA'  -\int_{\partial V} G(r';r) \vec 0 \cdot dA' \\
\varphi (r) &= \int_{\partial V} V_0 \nabla'G(r';r) \cdot dA'  \\
\end{align}
$$
Now, we can use the free space electrostatic green's function $G(r'; r) = \frac{1}{4\pi} \frac{1}{|r' - r|}$. Taking the grad of this function in spherical coordinates gives

Using the fact that our setup is rotationally symetric we can limit our $r$ to the $z$-axis and from their apply the cosine law:
![[Pasted image 20260915163428.png|424]]
With $|r'|$ being fixed at $R$ we get:
$$
\begin{align}
G(r';r) &= \frac{1}{4\pi} \frac{1}{r^2 + R^2 - rR\cos\phi}
\end{align}
$$
and so our integral

