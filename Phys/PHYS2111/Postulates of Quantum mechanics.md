## Postulate 1
The state of a particle is represented by a **vector** $\ket{\psi (t)}$ in a **Hilbert space**.
## Postulate 2
For every observable in classical mechanics there exists a corresponding **linear**, **hermitian** operator in quantum mechanics
## Postulate 3
The measurement of an observable $\Omega$ in quantum mechanics on a state $\ket \Psi$ will yield one of the eigenvalues of $\hat \Omega$, $\omega$ with probability $P(\omega) = |\braket{\omega | \Psi}|^2$. After the measurement the state will change from $\ket \Psi$ to $\ket \omega$.

## Postulate 4
$$
\begin{align}
i \hbar \frac{\partial \Psi}{\partial t} = \hat H \Psi
\end{align}
$$

## Notes
### Some notional conventions
- In QM we write observables as capital letters like $\Omega$ and we write their corresponding operators with a hat like $\hat \Omega$.
- We also write the eigenvalues and eigenvectors with the lowercase letter like $\omega_i$ and $\ket {\omega_i}$ respectively.
### A note on phase
Because QM only predicts probabilities and because the probability is given by an inner product squared we have that the absolute phase of two vectors does not matter only their relative phase matters:
$$
\begin{align}
|\braket{e^{i\phi}u|e^{i\phi}v}|^2 &= |\braket{u|e^{-i\phi}e^{i\phi} | v}|^2 \\
&= |\braket{u|e^{-i\phi}e^{i\phi} | v}|^2 \\
\end{align}
$$
<% tp.file.cursor(2) %>