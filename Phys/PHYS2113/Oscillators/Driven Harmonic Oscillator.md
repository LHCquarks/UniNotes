We have seen simple harmonic oscillators and their generalization in the dampened harmonic oscillators, now we generalize again to reach the driven harmonic oscillator. 

The equation of motion of a driven harmonic oscillator is
$$
\begin{align}
\ddot x + 2\beta \dot x + \omega_0^2 = f(t)
\end{align}
$$
Where $f(t)$ is a driving force that propels the harmonic oscillator
## Linear differential operators
There is a special class of operators called **linear differential operators** which as one may guess are linear and contain derivatives. The operator in question in the above equation is
$$
\begin{align}
\hat D[x] &= \left(\frac{d^2}{dt^2} + 2\beta\frac{d}{dt} + \omega_0^2\right)x \\
&= \frac{d^2x}{dt^2} + 2\beta\frac{dx}{dt} + \omega_0^2x \\
&= \ddot x + 2\beta \dot x + \omega_0^2x \\
\end{align}
$$
Given the 