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
and thus our solution is $x(t) = C_1 e^{i\omega t} + C_2 e^{-i\omega t}$. Asserting that $x \in \mathbb R$ we can simply take the real part of this expression
