## Gauss's law
Gauss's law in integral form states:
$$
\begin{align}
\oint_{\partial S} \vec E \cdot  d\vec A &= \frac{q_{\text {enc}}}{\epsilon_0}
\end{align}
$$
This essentially means that the electric flux out of any surface is proportional to the charge enclosed in the surface.

Using the divergence theorem we get:
$$
\begin{align}
\iiint_S \nabla \cdot \vec E d\tau &= \frac{1}{\epsilon_0} \iiint_S \rho d\tau \\
\nabla \cdot \vec E &= \frac{\rho}{\epsilon_0} \\
\end{align}
$$
Very cool
## Using the differential form of Gauss's law for problems
Suppose that $\vec E = k r^3 \hat r$. Find $\rho$
$$
\begin{align}
\nabla \cdot \vec E &= \frac{1}{r^2} \frac{\partial}{\partial r}(r^2 \vec E_r) \\
&= \frac{1}{r^2} \frac{\partial}{\partial r} (r^2 kr^3) \\
&= \frac{1}{r^2} 5kr^4 \\
&= 5kr^2 \\
\rho &= 5\epsilon_0kr^2 \\
\end{align}
$$
## Curl of the Electric field
Because $\vec E = -\nabla V$ and we assume that $V$ is cont differentiable then we get that $\nabla \times \vec E = 0$.

