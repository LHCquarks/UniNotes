We can represent the spin of a particle as a linear combination of the spins $\ket u$ (up) and $\ket d$ (down).

Then in our basis $\pmatrix{1 \\ 0} = \ket u, \pmatrix{0 \\ 1} = \ket d$ we have the operator $\hat \sigma_3 = \pmatrix{1 & 0 \\ 0 & -1}$ which is called the 3rd Pauli spin matrix. Using the postulates of QM we get:

If $\ket \Psi = \ket u$ then $\hat \sigma_3 \ket \Psi = \pmatrix{1 \\ 0} = 1 \ket u$. Thus measuring $\hat \sigma_3$ returns 1 and keeps our particle in the $\ket u$ state.

If $\ket \Psi = \ket d$ then $\hat \sigma_3 \ket \Psi = \pmatrix{0 \\ -1} = -1 \ket d$. Thus measuring $\hat \sigma_3$ returns $-1$ and keeps our particle in the $\ket d$ state.

If $\ket \Psi = \frac{1}{\sqrt{2}} \ket u + \frac{1}{\sqrt 2} \ket d$ then when measuring with $\hat \sigma_3$ we have a $|\braket{u | \Psi}|^2 = \frac{1}{2}$ chance to get $-1$thus putting $\ket \Psi$ into $\ket u$. We also have a $|\braket{d | \Psi}|^2 = \frac{1}{2}$ chance to get $-1$ putting $\ket \Psi$ into $\ket d$
