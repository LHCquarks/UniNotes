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
### Homogeneous equations
Suppose we have a general differential operator $\hat D$ and want to solve the equation $\hat D [x] = 0$. This equation is called a **homogeneous** linear differential equation. Suppose then we have two solutions to this differential equation, $x_1(t), x_2(t)$ then we can make a new solution to the DE by forming a linear combination of the two solutions
$$
\begin{align}
\hat D[\lambda x_1 + \mu x_2] &= \lambda \hat D[x_1] + \mu \hat  D[x_2] \\
&= \lambda 0 + \mu 0 \\
&= 0
\end{align}
$$
### Non-Homogeneous equations 
Now suppose we have the equation $\hat D[x] = f(t)$. This type of equation is called **Non-Homogeneous**. Take 2 solutions to this equation $x_1, x_2$  and consider their difference:
$$
\begin{align}
\hat D[x_2 - x_1] &= \hat D[x_2] - \hat D[x_1] \\
&= f(t) - f(t) \\
&= 0
\end{align}
$$
Therefore the difference between two solutions of our **Non-Homogeneous** case satisfy the **Homogeneous** case. This is really interesting as this would imply that $x_2 - x_1 = x_H \implies x_2 = x_1 + x_H$ for all solutions to the **Non-Homogeneous** equation and thus all solutions to the non-homogeneous case can be formed from one solution and all the solutions for the homogeneous case.

In practice solving these equations look like finding a single function that solves the non-homogeneous case and from there adding the solutions of the homogeneous case to get the general solution. This is mostly done through the method of knowing the answer beforehand.
## Sinusoidal driving force
Sinusoidal driving forces are very common in the real world (AC current, Rotating objects, EM waves ect) and they have analytic solutions. Further, we can turn all periodic functions into summations of sin / cos function by Fourier theory.

Say that $f(t) = f_0\cos(\omega t)$ then we can write our equation as:
$$
\begin{align}
\ddot x + 2\beta \dot x + \omega_0^2 &= f_0 \cos(\omega t) \\
\end{align}
$$
We can extend this equation into the complex plain with:
$$
\begin{align}
\ddot x + 2\beta \dot x + \omega_0^2 &= f_0 e^{i\omega t} \\
\end{align}
$$
We will take the ansatz $x(t) = Ce^{i\omega t}$:
$$
\begin{align}
\ddot x + 2\beta \dot x + \omega_0^2 &= f_0 e^{i\omega t} \\
\left(-\omega^2 + 2i\beta \omega + \omega_0^2\right)Ce^{i\omega t} &= f_0e^{i \omega t} \\
\left(-\omega^2 + 2i\beta \omega + \omega_0^2\right)C &= f_0 \\
C &= \frac{f_0}{\omega_0^2 - \omega^2 + 2i\beta \omega} \\
\end{align}
$$
We can then express our $C$ in the form $C = A e^{-i\delta}$ with:
$$
\begin{align}
A &= \frac{f_0}{\sqrt{(\omega_0^2 -\omega^2)^2 + 4\beta^2\omega^2}} \\
\delta &= \arctan\left(\frac{2\beta\omega}{\omega_0^2 - \omega^2}\right)
\end{align}
$$
Thus our particular solution to the equation is given by
$$
\begin{align}
x_p(t) &= \text{Re}\left(A e^{-i\delta}e^{i\omega t}\right) \\
&= \text{Re}\left(Ae^{i(\omega t - \delta)}\right) \\
&= A\cos(\omega t - \delta)
\end{align}
$$
and so the general solution is given by:
$$
\begin{align}
x(t) = A\cos(\omega t - \delta) + C_1e^{r_1 t} + C_2 e^{r_2 t}
\end{align}
$$
Further, because the homogeneous case vanishes as $t$ gets large we eventually get left with $x_p(t)$. Because the limiting case of all solutions does not care for the coefficients the limiting solution is called an **attractor** solution whilst all other parts are called the **transient** solutions.

