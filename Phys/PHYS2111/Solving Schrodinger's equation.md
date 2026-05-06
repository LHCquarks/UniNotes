	## General method
1. Find / get given $\hat H$
2. Find / get given $\ket {\Psi(0)}$
3. Find the eigenvalues and eigenvectors of the time independent Schrodinger equation:
$$
\begin{align}
\hat H \ket {\Psi_i} &= E_i \ket{\Psi_i}
\end{align}
$$
4. Use the initial state vector along with the eigenvectors to find the initial coefficients of our wave function using:
$$
\begin{align}
\alpha_i(0) &= \braket{\Psi_i | \Psi(0)}
\end{align}
$$
5. We now rewrite $\ket {\Psi(0)}$ as 
$$
\begin{align}
\ket {\Psi(0)} &= \sum_i \alpha_i(0) \ket {\Psi_i}
\end{align}
$$
6. Finally we replace $\alpha_i(0)$ with $\alpha(t) = \alpha_i(0)e^{-iE_it/\hbar}$ to get
$$
\begin{align}
\ket {\Psi(t)} = \sum_i \alpha_i(0) e^{-iE_it/\hbar} \ket{\Psi_i}
\end{align}
$$
These eigenstates are also known as stationary states as if our particle is in a single one of these then it remains in over time.

## Examples
### $\hat H = -\mu_bB\sigma_z$
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


