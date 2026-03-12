In the time just before quantum mechanics, two equations were found that seemed to describe this weird world and using these produced semi-classical mechanics. They were:
- Planks equation $E = h \nu = \hbar \omega$ 
- and the deBroglie wavelength $p = h/\lambda = \hbar k$

Assuming particles follow the wave equation the Schrodinger equation was derived:
$$
\begin{align}
i\hbar\frac{\partial \Psi}{\partial t} = \hat H \Psi =  - \frac{\hbar^2}{2m} \frac{\partial^2 \Psi}{\partial x^2} + V\Psi
\end{align}
$$

In this equation:
- $\Psi$ represents the wave function, a solution to the equation
- $i$ is the imaginary unit
- $\hbar$ is a constant which equals $\hbar = 1.05 \times 10^{-34}$Js
- $\hat H$ is the Hamiltonian operator (more on that later)
- $m$ is the mass of the particle
- $V$ is the potential energy at the specified location
## Properties the wave function has in 1d
- The wave function $\Psi(x, t)$ is a complex valued function
- The probability density is derived as $P(x, t) = \Psi^*(x, t) \Psi(x, t) = |\Psi(x, t)|^2$
- The probability distribution should tend to zero as we move further away or: $\lim_{x \rightarrow \infty} P(x, t) = 0$
- The wave function and it's derivative should be continuous and differentiable* and single valued
- There should be "probability currents" (probability should have to flow to neighboring points in space rather than teleporting)
- The wave function should contain all necessary information about the system to make predictions
- There are limits on the certainty with which we can measure certain properties simultaneously
	- $\Delta x \Delta p \ge \hbar/2$
	- $\Delta E \Delta t \ge \hbar / 2$
- Tells us how the system evolves in time
- The pdf of the wave function remains normalized over time
## Operators
Just like the **matrix** mechanics part of the course operators are objects that we apply to our wave function to measure certain things.

Common operators include:
$$
\begin{align}
\hat p &= - i \hbar \frac{\partial}{\partial x}, \\
\hat x &= x
\end{align}
$$
## Expectation values
To find the "average" value of a property of our wave function we take the **expectation value** of our wave function after applying the operator. This is denoted by $\braket {\hat A}$ where $\hat A$ is our operator.

This then expands to:
$$
\begin{align}
\braket \hat A &=  \braket {\Psi | \hat A \Psi}\\
&= \int_{-\infty}^\infty \Psi^* \hat A \Psi dx
\end{align}
$$

Now because properties of particles are souly real we get that
$$
\begin{align}
\braket \hat A ^* = \braket \hat A
\end{align}
$$ and expanding this out we get:
$$
\begin{align}
\braket {\Psi | \hat A \Psi} ^* &= \braket{\Psi | \hat A  \Psi} \\
\braket {\hat A \Psi | \Psi} &= \braket{\Psi | \hat A  \Psi} \\
\end{align}
$$
And thus all real properties have **Hermitian** operators



