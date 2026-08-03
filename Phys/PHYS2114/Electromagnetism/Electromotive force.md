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

