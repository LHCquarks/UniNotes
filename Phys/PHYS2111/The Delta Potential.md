Say we had the potential function:
$$
\begin{align}
V(x) &= -\alpha \delta(x)
\end{align}
$$
In this case we can solve the SE in the region $\mathbb R \backslash \{0\}$ like so:
$$
\begin{align}
\hat H \ket {\psi_E} &= E \ket {\psi_E} \\
-\frac{\hbar^2}{2m}\frac{\partial^2 \psi_E}{\partial x^2} &= E \psi_E \\
\frac{\partial^2 \psi_E}{\partial x^2} &=-\frac{2mE}{\hbar^2} \psi_E \\
\end{align}
$$
## Bounded case
First we will consider the bound case where $E< 0$ and thus our solution becomes:
$$
\begin{align}
\psi_{E_0}(x) = Ae^{kx} + B e^{-kx} \\
\end{align}
$$
Applying these solutions to both the left and right regions we get the solutions:
$$
\begin{align}
\psi_{E_0}(x) =  \cases{
Ae^{kx} + Be^{-kx} & x < 0 \\
Ce^{kx} + De^{-kx} & x > 0 \\
}
\end{align}
$$
Requiring $\psi_{E_0}$ be normalize-able we get that $B, C = 0$.
Further, requiring that $\psi_{E_0}$ is continuous we find that $A = D$ so our solution becomes:
$$
\begin{align}
\psi_{E_0}(x) =
\cases{
Ae^{kx} &x < 0 \\
Ae^{-kx} & x > 0
}
\end{align}
$$
We can then incorporate the delta potential property around $x = 0$ by writing the SE:
$$
\begin{align}
\hat H \ket {\psi} &= E\ket{\psi} \\
-\frac{\hbar^2}{2m} \frac{\partial^2 \psi}{\partial x^2} - \alpha \delta(x) \psi  &= E\psi \\
\end{align}
$$
We then integrate both sides in the region $(-\varepsilon, \varepsilon)$ to get:
$$
\begin{align}
\int_{-\varepsilon}^\varepsilon -\frac{\hbar^2}{2m} \frac{\partial^2 \psi}{\partial x^2} dx  + \int_{-\varepsilon}^\varepsilon - \alpha \delta(x) \psi dx &= \int_{-\varepsilon}^\varepsilon E\psi dx \\
-\frac{\hbar^2}{2m} \left[\frac{\partial \psi}{\partial x}\right]_{-\varepsilon}^\varepsilon
-\alpha \psi(0) &= \int_{-\varepsilon}^\varepsilon E\psi dx\\
\end{align}
$$
Expanding with the bounded solution we found we get:
$$
\begin{align}
-\frac{\hbar^2}{2m} \left[-kA e^{-k\varepsilon} - kAe^{-k\varepsilon} \right] - \alpha A = E\int_{-\varepsilon}^\varepsilon \psi_{E_0} dx
\end{align}
$$
Finally, taking the limit as $\varepsilon \rightarrow 0$ we get:
$$
\begin{align}
-\frac{\hbar^2}{2m}(-2kA) - \alpha A = 0 \\
\frac{kA\hbar^2}{m} = \alpha A \\
\frac{k\hbar^2}{m} = \alpha \\
k = \frac{\alpha m}{\hbar^2} \\
\end{align}
$$
Therefore we find that $k$ can only take one value and so there is only one bound state.
We can also normalize it but that is too much effort so we will just leave the solution at:
$$
\begin{align}
\psi_{E_0}(x) = \cases{
Ae^{\alpha mx/\hbar^2} & $x \le 0$ \\
A e^{-\alpha m x / \hbar^2} & $x > 0$
}
\end{align}
$$
## Unbounded case
In the unbounded case we know the solutions to be:
$$
\begin{align}
\psi_{E_0}(x) = \cases{
Ae^{kx} + Be^{-kx} & $x < 0$ \\
Ce^{\beta x} + De^{-\beta x} & $x < 0$ \\
}
\end{align}
$$
Now because the solutions are continuous we will study the case of transmission vs reflection.
For this we will say that the