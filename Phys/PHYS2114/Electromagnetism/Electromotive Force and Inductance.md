The electromotive force (emf) is a "driving voltage" in a circuit. Due to all circuits leaking power there must be a driving source of power that is not in equilibrium. This would being annoying to model so we instead "sweep it under the rug" by packaging it up into one number $\varepsilon$.

## Ohms law with emf
If $R$ is the resistance of the rest of the circuit then by Ohm's law:
$$
\begin{align}
I &= \frac{\varepsilon}{R + R_{\text{int}}}
\end{align}
$$
However this implies that $V \not = \varepsilon$ because $I = \frac{V}{R}$. We can however, find a relation between $V$ and $\varepsilon$:
$$
\begin{align}
\frac{V}{R} &= \frac{\varepsilon}{R + R_{\text{int}}} \\
V &= \frac{\varepsilon R}{R + R_\text{int}}
\end{align}
$$
## Motional EMF and Faraday's Law
Faraday's law states:
$$
\begin{align}
\varepsilon &= -\frac{\partial \Phi}{\partial t}
\end{align}
$$
Thus changing $\Phi$ can produce an emf. Now the question is how can we change $\Phi$? From the definition of $\Phi$:
$$
\begin{align}
\Phi &= \int_A \vec B \cdot d\vec A
\end{align}
$$
so we can either vary $\vec B$ over time or $d\vec A$. 
### Electric generator
A generator consists of a loop of wire in a constant, uniform magnetic field. The loop is free to spin along an axis perpendicular to $\vec B$ with $\vec A$ making an angle of $\theta$ with the axis both perpendicular to $\vec \omega, \vec B$.
![[Pasted image 20260803113644.png]]
Thus $\vec B \cdot \vec A = BA\cos(\omega t)$ and so:
$$
\begin{align}
\Phi &= BA\cos(\omega t) \\
\varepsilon &= -\frac{\partial \Phi}{\partial t} \\
\implies \varepsilon &= BA\sin(\omega t) \\

\end{align}
$$
### Differential form of Faraday's law
By the definition of voltage $\varepsilon = \int_\gamma \vec E \cdot d\vec l$ we can get the differential form of Faraday's law:
$$
\begin{align}
\varepsilon &= -\frac{\partial \phi}{\partial t} \\
\int_{\partial A} \vec E\cdot  d\vec l &= -\frac{\partial}{\partial t} \int_{A} \vec B\cdot d\vec A \\
\int_{A} (\vec \nabla \times \vec E) \cdot d\vec A  &= \int_{A} - \frac{\partial \vec B}{\partial t}\cdot d\vec A
\end{align}
$$
Due to $A$ being arbitrary the intergrands must be equal hence:
$$
\begin{align}
\vec \nabla \times \vec E &= -\frac{\partial \vec B}{\partial t}
\end{align}
$$
## Self Inductance
Consider a loop of wire that carries a current of $I$. This current then creates a magnetic field and hence has a flux. The flux through this wire is proportional to the current in the wire by a factor called the inductance $L$ ($\Phi = L I$). 

$L$ depends on the shape and size of the wire.

By Faraday's law we get that
$$
\begin{align}
\varepsilon &= -L\frac{d I}{dt}
\end{align}
$$




