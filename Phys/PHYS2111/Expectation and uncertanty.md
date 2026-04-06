## Expectation values
It is natural to ask what is our expected value of a measurement?
Well do I have a formula for you!

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
This is a super easy formula to use!
## Uncertainty
Now what about uncertainty?
Well using the formula given from John HSC himself we have that $\text{Var}(\Omega) = \text{E}(\Omega^2) + \text{E}(\Omega)^2$  and thus translated into QM we get:
$$
\begin{align}
\sigma_{\Omega}^2 &= \braket{\Omega^2} - \braket{\Omega}^2 \\
&= \braket{\Psi | \hat \Omega \hat \Omega | \Psi} - \braket{\Psi | \hat \Omega| \Psi}^2
\end{align}
$$