We begin our derivation with Maxwell's equations with $\rho, J = 0$
$$
\begin{align}
\nabla \cdot E &= 0 \tag{1}\\
\nabla \cdot B &= 0 \tag{2}\\
\nabla \times E &= -\frac{\partial B}{\partial t} \tag{3}\\
\nabla \times B &= \frac{1}{c^2} \frac{\partial E}{\partial t} \tag{4} \\
\end{align}
$$
We will then take the Curl of equations $(3)$ and use the fact that $\nabla \times \nabla \times F = \nabla (\nabla \cdot F) - \nabla^2 F$ to get:
$$
\begin{align}
\nabla \times \nabla \times E &= -\nabla \times \frac{\partial B}{\partial t} \\
\nabla (\nabla \cdot E) - \nabla^2 E &= -\frac{\partial }{\partial t} \left(\nabla \times B\right) \\
0 - \nabla ^2 E &= -\frac{\partial }{\partial t} \left(\frac{1}{c^2} \frac{\partial E}{\partial t}\right) \tag{1, 4} \\
\nabla ^2 E &= \frac{1}{c^2} \frac{\partial^2 E}{\partial t^2}
\end{align}
$$
This is the wave equation.

If we assume that the vectorial nature of our EM-wave does not matter then we can substitute a scalar field for $\vec E(\vec r, t) \rightarrow U(\vec r, t)$:
$$
\begin{align}
\nabla^2U = \frac{1}{c^2}\frac{\partial^2U}{\partial t^2}
\end{align}
$$
Also assuming that our $U(\vec r, t)$ takes the form $U(\vec r, t) = U(\vec r)e^{-i\omega t}$ we get the Helmhotz equation:
$$
\begin{align}
\nabla^2 U(\vec r) + \frac{\omega^2}{c^2}U(\vec r) &= 0 \\
\nabla^2 U + k^2U &= 0 \\
\end{align}
$$
