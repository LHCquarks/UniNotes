Stationary states are solutions to the Schrodinger equation where the potential is independent in time. Thus $V(x, t) = V(x)$.

We can thus take $\Psi(x, t) = \psi(x) \phi(t)$ 
Plugging this into the Schrodinger equation we get:
$$
\begin{align}
i \hbar \frac{\partial \Psi}{\partial t} &= -\frac{\hbar^2}{2m} \frac{\partial^2 \Psi}{\partial x^2} + V(x) \Psi \\
i \hbar \psi \frac{\partial \phi}{\partial t} &= -\frac{\hbar^2}{2m} \phi\frac{\partial^2 \psi}{\partial x^2} + V(x)\psi\phi \\
\frac{1}{\phi}i \hbar \frac{\partial \phi}{\partial t} &= -\frac{\hbar^2}{2m\psi} \frac{\partial^2 \psi}{\partial x^2} + V(x) \\
\end{align}
$$
The only way that both sides are equal to each other is if both sides are constant thus:
$$
\begin{align}
i\hbar \frac{d\phi}{dt} &= E \phi(t) \\
\int i\hbar \frac{d\phi}{\phi} &= \int E dt\\
i\hbar \ln(\phi) &= Et + a\\
\ln(\phi) &= \frac{Et + a}{i\hbar}\\
\phi(t) &= e^\frac{Et + a}{i\hbar}\\
\phi(t) &= Ae^{-i\frac{Et}{\hbar}}\\
\end{align}
$$
for some constants $A, E$. For the other equation:
$$
\begin{align}
E &= -\frac{\hbar^2}{2m\psi} \frac{d^2 \psi}{d x^2} + V(x) \\
E - V(x) &= -\frac{\hbar^2}{2m\psi(x)} \frac{d^2 \psi}{d x^2} \\
\end{align}
$$
This type of equation often produces bound states, free states and mixed states.

If we define $\psi_n(x)$ as an eigenstate with an eigenvalue $E_n$ of the Hamiltonian so $\hat H \psi = E_n \psi$ then we know that our eigenstates are orthonormal as $\hat H$ is **Hermitian** and thus:
$$
\begin{align}
\int_{-\infty}^\infty \psi_m^*\psi_ndx &= \delta_{m, n}
\end{align}
$$
This hints that our solutions to the Schrodinger equation are linear combinations of our eigenstates.

Thus $\Psi(x, t) = \sum a_n\Psi_n(x, t) = \sum a_n\psi_n(x) e^{-i\frac{E_n t}{\hbar}}$ 


