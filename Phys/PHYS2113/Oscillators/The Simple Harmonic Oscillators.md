Most objects in the real world are not moving. This is because they are already sitting at a local minimum of their potential. 

Considering a general potential function $U(x)$ that has a minimum at $x = x_0$ we understand that $U'(x_0) = 0$ and thus the Taylor expansion of $U$ is given by
$$
\begin{align}
U(x) &= c + U'(x_0)(x - x_0) + \frac{k}{2} U''(x_0)(x- x_0)^2 + \dots \\
&= c + \frac{1}{2} U''(x_0)(x- x_0)^2 + \dots
\end{align}
$$
It is then a good approximation to write $U(x) = \frac{k}{2}(x - x_0)^2$ as constants are redundant when talking about potentials.

Finding solutions to many problems are then found with $U(x) = \frac{k}{2}(x - x_0)^2$.
## The solution
Assuming that $x_0 = 0$  and then deriving for the force we get $F = -kx$ and solving Newton's equation gives
$$
\begin{align}
m\ddot x + kx &= 0 \\
\ddot x + \frac{k}{m}x &= 0 \\
\end{align}
$$
We can then also write $\omega^2 = \frac{k}{m}$ and thus our EOM is
$$
\begin{align}
\ddot x + \omega^2 x &= 0
\end{align}
$$
Substituting in an ansatz of $x = e^{\alpha t}$ we get
$$
\begin{align}
\alpha^2 x + \omega^2 x &= 0 \\
\alpha^2 &= -\omega^2 \\
\alpha &= \pm i\omega \\
\end{align}
$$
and thus our solution is $x(t) = C_1 e^{i\omega t} + C_2 e^{-i\omega t}$. Asserting that $x \in \mathbb R$ we know that $x^* = x$ and so $C_1^* e^{-i\omega t} + C_2^* e^{i \omega t} = C_1 e^{i\omega t} + C_2 e^{-i \omega t}$. By inspection we know $C_1 = C_2^*$ and vice versa.

This has other forms such as:
$$
\begin{align}
x(t) &= C_1 e^{i \omega t} + C_2 e^{-i \omega t} \\
x(t) &= A\cos(\omega t + \phi ) \\
x(t) &= \text{Re}(Ae^{i\omega t + \phi }) \\
\end{align}
$$
## Higher dimensions
Taking $U(x) = \frac{\omega^2}{2}x^2 + \frac{\omega^2}{2}y^2 + \dots$ we can use Lagrangian mechanics to find the equations of motion:
$$
\begin{align}
\mathcal L &= \frac{m}{2}\left(\dot x^2 + \dot y^2 + \dot z^2\right) - \frac{\omega^2}{2}\left(x^2 + y^2 + z^2\right) \\
\end{align}
$$
Because all the components are independent so too will be their differential equations and thus for all coordinates
$$
\begin{align}
x(t) = A\cos(\omega t + \phi)
\end{align}
$$

These solutions are fairly obviously periodic iff $\frac{\omega_x}{\omega_y}, \frac{\omega_y}{\omega_z}, \frac{\omega_x}{\omega_z} \in \mathbb Q$.
## Damped simple harmonic oscillator
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
First, case (1) simply reduces back to the simple harmonic oscillator with the equation
$$
\begin{align}
x(t) = C_1 e^{i\omega_0t} + C_2e^{-i\omega_0 t}
\end{align}
$$

Next, case (2) still results in $\beta^2  - \omega_0^2 < 0$ and thus we still get oscillations however now with a decay in in the amplitude. If $\omega_1^2 = \beta^2 - \omega_0^2$ then
$$
\begin{align}
x(t) &= e^{-\beta t}\left(C_1 e^{i\omega_1t} + C_2e^{-i\omega_1 t}\right)
\end{align}
$$
