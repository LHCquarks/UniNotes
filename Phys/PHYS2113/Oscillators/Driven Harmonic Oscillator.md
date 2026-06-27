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