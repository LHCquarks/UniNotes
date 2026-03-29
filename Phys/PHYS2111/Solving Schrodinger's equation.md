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
## Examples
