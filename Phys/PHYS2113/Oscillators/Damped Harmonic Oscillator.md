## General solution
Often our systems are not quite as ideal as that required in the simple harmonic oscillator. Usually the energy in our systems is lost over time an effect which can often be modeled as a linear dependence on the motion $F_{\text{damped}} = -2\beta \dot x$ for low values of $\dot x$. 

Our equation of motion then becomes
$$
\begin{align}
\ddot x + 2 \beta \dot x + \omega_0^2 x &= 0
\end{align}
$$
As we did for the simple harmonic oscillator we will make the ansatz $x(t) = Ae^{rt}$ to get
$$
\begin{align}
r^2 + 2\beta r + \omega_0^2 &= 0 \\
r_1 &= -\beta + \sqrt{\beta^2 - \omega_0^2} \\
r_2 &= -\beta - \sqrt{\beta^2 - \omega_0^2} \\
\end{align}
$$
and thus our solution becomes
$$
\begin{align}
x(t) &= e^{-\beta t} \left(C_1 e^{\sqrt{\beta^2 - \omega_0^2}t} + C_2 e^{-\sqrt{\beta^2 - \omega_0^2}t}\right)
\end{align}
$$
Very interesting.

We can split this equation into a few cases
$$
\begin{align}
\beta &= 0 \tag 1\\
|\beta| &< |\omega_0| \tag 2\\
|\beta| &> |\omega_0| \tag 3\\
|\beta| &= |\omega_0| \tag 4\\
\end{align}
$$
## Simple harmonic motion
Case (1) simply reduces back to the simple harmonic oscillator with the equation
$$
\begin{align}
x(t) = C_1 e^{i\omega_0t} + C_2e^{-i\omega_0 t}
\end{align}
$$
## Weakly damped harmonic oscillator
Case (2) still results in $\beta^2  - \omega_0^2 < 0$ and thus we still get oscillations however now with a decay in in the amplitude. If $\omega_1^2 = \beta^2 - \omega_0^2$ then
$$
\begin{align}
x(t) &= e^{-\beta t}\left(C_1 e^{i\omega_1t} + C_2e^{-i\omega_1 t}\right)
\end{align}
$$
Pots of this solution involve sinusoidal curves within an exponential envelope as shown bellow:

## Strongly damped harmonic oscillator
Case (3) results in $\beta^2 - \omega_0^2 > 0$ and so will no longer have sinusoidal motion. We then find that our solution is of the form
$$
\begin{align}
x(t) &= C_1 e^{-\beta + \sqrt{\beta^2 - \omega_0^2} t} + C_2 e^{-\beta - \sqrt{\beta^2 - \omega_0^2} t}
\end{align}
$$
It can be seen that $\left|-\beta + \sqrt{\beta^2 - \omega_0^2}\right| < \left|-\beta - \sqrt{\beta^2 - \omega_0^2}\right|$ and thus in the limit as $t \rightarrow \infty$ the first term is the only one that is important.

Plots of the above curves are below:

## Critically damped oscillator

## The fastest decay rate