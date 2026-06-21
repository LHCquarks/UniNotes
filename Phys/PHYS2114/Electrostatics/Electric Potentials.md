## Definition
The electric potential (voltage) is defined by:
$$
\begin{align}
V(\vec x) = -\int_{\vec x_0}^\vec x \vec E \cdot d\vec s
\end{align}
$$
Where $V(\vec x_0) = 0$.

Whilst the point $x_0$ where we define $V(x_0) = 0$ is arbitrary, we have to be careful to make sure it is bounded otherwise we nonsensical values. Because in reality charges do not extend to infinity so too do realistic electric fields and thus setting $V(\infty) = 0$ is very common but any bounded point works just as well.
## Differential relation to $\vec E$
The fundamental theorem of line integrals states that
$$
\begin{align}
f(\vec b) - f(\vec a) = \int_{\vec a}^{\vec b} \nabla f \cdot d\vec s
\end{align}
$$
This would imply by the definition of $V(\vec x)$ the following relationship:
$$
\begin{align}
\vec E = -\nabla V
\end{align}
$$
This is how we take a voltage and turn it into it's electric field.
## Advantages of voltage
Because the voltage at a point is a scalar function it is often far easier to derive and work with and because it is then so easy to turn it into the electric field it is often advantages to first work out the voltage and then derive the electric field rather than solving for $\vec E$ directly.
## New version of Gauss's law
Gauss's law states:
$$
\begin{align}
\nabla \cdot \vec E = \frac{\rho}{\epsilon_0}
\end{align}
$$
We can then sub in our new equation for $\vec E$ to get:
$$
\begin{align}
\nabla^2 V = -\frac{\rho}{\epsilon_0}
\end{align}
$$
This is called **Poisson's equation**.
In the special case where $\rho = 0$ we have **Laplace's equation**:
$$
\begin{align}
\nabla^2V = 0
\end{align}
$$
We will see more on this equation in the special techniques section.
## Finding electric potentials
To find the electric potential of some charge distribution we make use of the potential of a point charge
$$
\begin{align}
V(\vec r) &= \frac{1}{4\pi\epsilon_0}\frac{q}{\mathscr r}
\end{align}
$$
Invoking the law of super position the voltage for a set of discrete charges is given by
$$
\begin{align}
V(\vec r) &= \frac{1}{4\pi\epsilon_0}\sum_i\frac{q_i}{\mathscr r_i}
\end{align}
$$
and thus for a continuous charge distribution:
$$
\begin{align}
V(\vec r) &= \frac{1}{4\pi\epsilon_0}\int\frac{\rho}{\mathscr r}d\tau'
\end{align}
$$


