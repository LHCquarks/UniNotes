Topics to cover:
## Math of QM
### State vector spaces are cool
### Define the duel space
### Bra-ket notation
### Inner product space
1. $\braket{v|w} = \braket{w|v}^*$
2. $\braket{v|v} \ge 0$
	- We also need $\braket{v|v} = 0$ iff $\ket v = \ket 0$
3. $\braket{u|av + bw} = a\braket{u|v} + b\braket{u|w}$
- Length
- Exercise: proof of linearity of the bra
$$
\begin{align}
A &= \braket{au + bv | w} \\
&= \braket {w | au + bv}^* \tag {1}\\ 
&= a^*\braket{w|u}^* + b^*\braket{w|v}^* \tag{3}\\
&=  a^*\braket{u|w} + b^*\braket{v|w} \\
\end{align}
$$
- Orthogonality
- Inner product for complex vectors
### Operators
- Show the notation $\hat E \ket \psi = \ket{\hat E \psi}$
Exercise:
apply the mysterious operator
$$
\begin{align}
\sigma_y &= \pmatrix{0 & -i \\ i & 0}
\end{align}
$$
to the vectors
$$
\begin{align}
\ket {u} &= \pmatrix{1 \\ 0} \\
\ket {d} &= \pmatrix{0 \\ 1} \\
\ket {l} &= \frac{1}{\sqrt 2}\pmatrix{-i \\ 1} \\
\ket {r} &= \frac{1}{\sqrt 2}\pmatrix{i \\ 1} \\
\end{align}
$$
- brief recap of eigenvectors / eigenvalues (how to find them and what they are)
- Describe the importance of eigenvectors and eigenvalues to QM
Exercise:
find the eigenvalues / eigen vectors of the operator:
$$
\begin{align}
\sigma_z &= \pmatrix{1 & 0 \\ 0 & -1}
\end{align}
$$
### Hermitian adjoint
- Define the hermitian adjoint
- Show $(\hat A ^\dagger)^\dagger = \hat A$
Exercise:
show
$$
\begin{align}
(\hat A + \hat B)^\dagger &= \hat A^\dagger + \hat B^\dagger \\
(\hat A \hat B)^\dagger &= \hat B^\dagger\hat A^\dagger
\end{align}
$$
- State hermitian adjoint of a scalar
- State hermitian adjoint of bra / ket
- State hermitian adjoint of a matrix
### Orthonormal eigenbasis
### Kronecker delta
### Hermitian operators
- Definition
- Decomposition into hermitian and anti-hermitian
- Eigenvalues are real, eigenvectors are orthogonal
Exercise:
Is $\hat A$ hermitian?
$$
\begin{align}
\sigma_x &= \pmatrix{0 & 1 \\ 1 & 0}
\end{align}
$$
### Unitary operators
- Definition
- Preserve inner products
## Postulates of QM
### Postulate 1
The state of a particle is represented by a **vector** $\ket{\psi (t)}$ in a **Hilbert space**.
### Postulate 2
For every observable in classical mechanics there exists a corresponding **linear**, **hermitian** operator in quantum mechanics
### Postulate 3
The measurement of an observable $\Omega$ in quantum mechanics on a state $\ket \Psi$ will yield one of the eigenvalues of $\hat \Omega$, $\omega$ with probability $P(\omega) = |\braket{\omega | \Psi}|^2$. After the measurement the state will change from $\ket \Psi$ to $\ket \omega$.

Exercise:
Consider a wave function in the basis $\ket 1, \ket 2, \ket 3$ given by
$$
\begin{align}
\ket \psi &= N (-5 \ket 1 + (i  + 3) \ket 2 + 2\ket 3)
\end{align}
$$
Find:
- $N$ to normalize the wave function 
- probability $\ket \psi$ is in state $\ket 1$
- probability $\ket \psi$ is in state $\ket 2$
- probability $\ket \psi$ is in state $\ket 3$
### Postulate 4
$$
\begin{align}
i \hbar \frac{\partial \Psi}{\partial t} = \hat H \Psi
\end{align}
$$

## Solving the SE
### Separation of variables
State that the solution of the SE is unique. Assert our solutions shall be in the form $\Psi(x, t) = \psi(x)\phi(t)$ and get the eigenvector equations
### Example
$\hat H = -\mu_bB\sigma_z$
An electron in a magnetic field pointing in the $z$ direction has a Hamiltonian of $\hat H = -\mu_bB\sigma_z$ where:
- $\mu_b$ is the Bohr magnaton which measures the magnetic dipole moment of an electron
- $B$ is the strength of the magnetic field
- $\sigma_z$ is the 3rd Pauli spin matrix $\pmatrix{1 & 0 \\ 0 & -1}$
If you wish to further decompose this equation $\mu_b$ equals $\frac{e\hbar}{2m_e}$ where:
- $e$ is the charge of the electron
- $m_e$ is the mass of the electron
It is also given that the initial state of our particle is $\ket {\Psi(0)} = \frac{1}{\sqrt{2}} \pmatrix{1 \\ 1}$
1. $\hat H = -\mu_b B \sigma_z$
2. $\ket {\Psi(0)} = \frac{1}{\sqrt{2}} \pmatrix{1 \\ 1}$
3. Eigenvalues  / Eigenvectors of $\hat H$:
Eigenvalues given by:
$$
\begin{align}
\det(\hat H - E_i I) &= 0 \\
\begin{vmatrix} 
-\mu_b B - E_i & 0 \\ 0 & \mu_b B - E_i
\end{vmatrix}
&= 0 \\
-(\mu_b B+ E_i)(\mu_b B - E_i) &= 0 \\
(\mu_b B+ E_i)(\mu_b B - E_i) &= 0 \\
E_i &= \pm \mu_b B \\
\end{align}
$$
Eigenvectors given by:
$\ket {E_+}$:
$$
\begin{align}
&\left (
\begin{array}{cc|c}
- \mu_b B - \mu_b B & 0 & 0 \\
0 & \mu_b B - \mu_b B & 0
\end{array}
\right ) \\
\rightarrow & 
\left (
\begin{array}{cc|c}
- \mu_b B - \mu_b B & 0 & 0 \\
0 & 0 & 0
\end{array}
\right ) \\
\rightarrow & \ket {E_+} = \pmatrix{0 \\ \lambda}
\end{align}
$$
We can set our lambda equal to one so we get $\ket {E_+} = \pmatrix{0 \\ 1}$
$\ket {E_-}$:
$$
\begin{align}
&\left (
\begin{array}{cc|c}
- \mu_b B + \mu_b B & 0 & 0 \\
0 & \mu_b B + \mu_b B & 0
\end{array}
\right ) \\
\rightarrow & 
\left (
\begin{array}{cc|c}
0 & 0 & 0 \\
0 & \mu_b B + \mu_b B & 0
\end{array}
\right ) \\
\rightarrow & \ket {E_-} = \pmatrix{\lambda \\ 0}
\end{align}
$$
We can set our lambda equal to one so we get $\ket {E_-} = \pmatrix{1 \\ 0}$
4. Find our initial coefficients:
$$
\begin{align}
\alpha_+ (0) &= \braket{E_+ | \Psi(0)} \\
&= \pmatrix{1 & 0} \frac{1}{\sqrt{2}} \pmatrix{1 \\ 1} \\
&= \frac{1}{\sqrt 2} \\
\alpha_- (0) &= \braket{E_- | \Psi(0)} \\
&= \pmatrix{0 & 1} \frac{1}{\sqrt{2}} \pmatrix{1 \\ 1} \\
&= \frac{1}{\sqrt 2} \\
\end{align}
$$
5. Initial state vector:
$$
\begin{align}
\ket {\Psi(0)} &= \frac{1}{\sqrt{2}} \ket{E_+} + \frac{1}{\sqrt{2}} \ket{E_-}
\end{align}
$$
6. Final state vector:
$$
\begin{align}
\ket{\Psi(t)} &= \frac{1}{\sqrt 2} e^{-i E_+ t / \hbar} \ket{E_+} + \frac{1}{\sqrt 2} e^{-iE_- t /\hbar} \ket{E_-} \\
&= \frac{1}{\sqrt 2} \pmatrix{e^{-iE_+t/\hbar} \\ e^{-iE_-t/\hbar}} \\
&= \frac{1}{\sqrt 2} \pmatrix{e^{-i\mu_b Bt/\hbar} \\ e^{i\mu_b Bt/\hbar}} \\
\end{align}
$$
## Expectation and uncertainty
The expectation value of a certain observable $\Omega$ acting on $\ket \Psi$ is represented with $\braket \Omega$ and is given by:
$$
\begin{align}
\braket \Omega &= \sum_i \omega_i P_\Psi(\omega_i) \\
&= \sum_i \omega_i |\braket{\omega_i | \Psi}|^2 \\
&= \sum_i \omega_i \braket{\Psi | \omega_i} \braket{\omega_i | \Psi} \\
&= \sum_i \omega_i \bra{\Psi} \ket{\omega_i} \braket{\omega_i | \Psi} \\
&= \bra\Psi \sum_i \omega_i \ket{\omega_i} \bra{\omega_i} \ket{\Psi} \\
&= \bra\Psi \hat \Omega \ket{\Psi} \\
\end{align}
$$
Now what about uncertainty?
Well using the formula given from John HSC himself we have that $\text{Var}(\Omega) = \text{E}(\Omega^2) + \text{E}(\Omega)^2$  and thus translated into QM we get:
$$
\begin{align}
\sigma_{\Omega}^2 &= \braket{\Omega^2} - \braket{\Omega}^2 \\
&= \braket{\Psi | \hat \Omega \hat \Omega | \Psi} - \braket{\Psi | \hat \Omega| \Psi}^2
\end{align}
$$
Exercise:
Given that $\ket \psi = \frac{1}{2}\pmatrix{\sqrt{3} \\ 1}$ find:
$$
\begin{align}
\braket{\sigma_x} \\
\braket{\sigma_y} \\
\braket{\sigma_z} \\
\end{align}
$$
Exercise:
A particle has a wave function
$$
\begin{align}
\ket \psi &= \frac{1}{\sqrt {17}} \left[\matrix{-3i- 2 \\ 0 \\ -2} \right]
\end{align}
$$
and we define a hermitian operator
$$
\begin{align}
\hat \Omega &= \left[\matrix{0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 2}\right]
\end{align}
$$
What is $\braket{\Omega}$ and $P(0)$, $P(2)$

## Multiple particles
- Show tensor product
- Show how it works
- State conventions
Apply it on 



