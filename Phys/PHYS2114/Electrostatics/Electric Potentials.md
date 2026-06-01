---
aliases:
---
## Definition
The electric potential (voltage) is defined by:
$$
\begin{align}
V(\vec x) = -\int_{\vec x_0}^\vec x \vec E \cdot d\vec s
\end{align}
$$
Where $V(\vec x_0) = 0$.
## Relation to $\vec E$
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

