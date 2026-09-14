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
