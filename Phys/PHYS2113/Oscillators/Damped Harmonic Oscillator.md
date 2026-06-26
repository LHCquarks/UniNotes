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
![[simple_harmonic_fig.svg]]
## Weakly damped harmonic oscillator
Case (2) still results in $\beta^2  - \omega_0^2 < 0$ and thus we still get oscillations however now with a decay in in the amplitude. If $\omega_1^2 = \beta^2 - \omega_0^2$ then
$$
\begin{align}
x(t) &= e^{-\beta t}\left(C_1 e^{i\omega_1t} + C_2e^{-i\omega_1 t}\right)
\end{align}
$$
Pots of this solution involve sinusoidal curves within an exponential envelope as shown below:
![[weakly_damped_plot.svg]]
## Strongly damped harmonic oscillator
Case (3) results in $\beta^2 - \omega_0^2 > 0$ and so will no longer have sinusoidal motion. We then find that our solution is of the form
$$
\begin{align}
x(t) &= C_1 e^{-\beta + \sqrt{\beta^2 - \omega_0^2} t} + C_2 e^{-\beta - \sqrt{\beta^2 - \omega_0^2} t}
\end{align}
$$
It can be seen that $\left|-\beta + \sqrt{\beta^2 - \omega_0^2}\right| < \left|-\beta - \sqrt{\beta^2 - \omega_0^2}\right|$ and thus in the limit as $t \rightarrow \infty$ the first term is the only one that is important.

Plots of the above curves are below
![[strongly_damped_plot.svg]]

## Critically damped oscillator
Case (4) results in $\sqrt{\beta^2 - \omega_0^2} = 0$ and thus our equation of motion becomes
$$
\begin{align}
x(t) &= e^{-\beta t} (C_1 + C_2) \\
&= Ae^{-\beta t}
\end{align}
$$
But wait there is a problem. This equation only has one free variable but we know we need two free variables to alter both the initial location and momentum. This means we are missing a solution. 

The solution we are missing is $x(t) = Bte^{-\beta t}$ and thus our general solution becomes
$$
\begin{align}
x(t) &= e^{- \beta t} (A + B t)
\end{align}
$$
plots of this solution are shown below
![[critically_damped_plot.svg]]
## The fastest decay rate
When we consider the above solutions we can see that they all involve some sort of exponential decay. Measuring their decay rate by their limiting decay factor (ie for case (3) the limiting decay factor was $\beta - \sqrt{\beta^2 - \omega_0^2}$) we get the following plot
![[decay_rate_plot.svg]]
As can be seen in the plot the fastest decaying curve is the critically damped case where $\beta = \omega_0$. This can be physically made sense of as before $\beta = \omega_0$, the oscillator overshoots the setups and so decays slower whilst after $\beta = \omega_0$ the oscillator losses too much energy too fast and thus reaches equilibrium slower like a ball in honey.