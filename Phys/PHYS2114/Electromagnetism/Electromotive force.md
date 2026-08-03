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



