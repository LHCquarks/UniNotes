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

If we assume that the vectorial nature of our EM-wave does not matter then we can substitute a scalar field for $\vec E(\vec r, t) \rightarrow U(\vec r, t)$ where $U = |\vec E|$:
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
Finally, we recognise the solution to this as a super position of plain waves:
$$
\begin{align}
U(\vec r, t) &= Ae^{i(\vec k \cdot \vec r - \omega t)}
\end{align}
$$
with $|\vec k| = \frac{\omega}{c}$. 
## Huygens-Fresnel formulation
Huygen proposed that given a wave front we can propagate it by treating each point of the wave front as point sources that add to form a new wave front:
![[Pasted image 20260925070801.png]]
As appart of this we need to figure out how a point source propigates. Let $\psi(r, t)$ be a point source wave, we know that we need a $e^{i(kr - \omega t)}$ term in our expression but if we just settle for that we get a problem. If we consider the intensity of the wave allong a circle of radius $R$ and sum it up to get $\Psi$ we get:
$$
\begin{align}
\psi(R, t) &= e^{i(kR - \omega t)} \\
I &= |\text{Re}(e^{i(kR - \omega t)})|^2 \\
|\psi|^2 &= \cos^2(kR - \omega t)\\
\Psi &= 2\pi R\cos^2(kR - \omega t)
\end{align}
$$
This is obviouly a problem as the intensity increases in magnitude at further $R$ meaning energy is being created from nowhere. To fix this we can divide by $r$ so our equations becomes:
$$
\begin{align}
\psi(r, t) &= \left(\frac{\mathscr A}{r}\right) e^{i(kr - \omega t)}
\end{align}
$$
where $\mathscr A$ is just a normalizing factor. 
### The Obliquity Factor
This moddel is great and all but there is another problem. In this moddel waves propigate both backwards and forwads equally. The simplest way to solve this is to just multiply by some term which favours forwards going waves and blocks out the contributions of backwards going waves.

To do this we multiply by some function $\kappa(\chi)$ where $\chi$ is the angle between the point we are looking at and the normal to the wavefront
![[Pasted image 20260925072843.png]]
This gives
$$
\begin{align}
\psi(r, t) &= \left(\frac{\mathscr A}{r}\right)e^{i(kr - \omega t)} \kappa(\chi)
\end{align}
$$
where $\kappa(\chi)$ can change depending on the theory and is usually $\kappa(\chi) = \frac{1 + \cos(\chi)}{2}$. 