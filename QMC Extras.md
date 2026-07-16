## Solving SE
When I solved SE for you guys I got to this point and pulled off some BS with functions and vectors. 
$$
\begin{align}
i\hbar\frac{1}{\phi}\frac{d\phi}{dt} \ket \psi &= \hat H \ket \psi
\end{align}
$$
I have a new way of thinking about it. Notice how the RHS of the equation has no dependence on time which means the LHS can not depend on time either. This means that
$$
\begin{align}
i\hbar \frac{1}{\phi(t)} \frac{d\phi}{dt}(t)
\end{align}
$$
Has no dependence on time and thus must be a constant we will call $E$. From here we recover the time independent SEs
$$
\begin{align}
i\hbar \frac{d\phi}{dt} &= E\phi(t) \\
\hat H\ket{\psi} &= E\ket\psi
\end{align}
$$
## A challenge
This setup is similar to the infinite square well but this time we will have it be finite.
Here the potential function is given by
$$
\begin{align}
V(x) &= 
\begin{cases}
0 & -a \le x \le a \\
V_0 & \text{otherwise}
\end{cases}
\end{align}
$$
where $V_0 > 0$.  We will also only consider the case where the total energy of the particle is less than the outer potential ($0 \le E < V_0$). These solutions are called the bound case as the particle is stuck in the box*.

### Scaffold
This is a rough guide on solving the equation with all the key checkpoints.
1. Solve SE inside the box
2. Solve SE outside the box
3. Assert the following boundary conditions
	1. The wave function is normalisable (otherwise it would not form a proper pdf)
	2. The wave function is continuous
	3. The wave function is continuously differentiable
4. With these boundary conditions u will arrive at a set of equations that all have to be true. State these or solve them numerically if u want