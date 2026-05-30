So far we have been doing QM on only one particle and one property of that particle (eg position or spin) but what if we want to solve a QM system with more than one particle?

The answer is we combine the vector spaces of our individual particles / properties into one vector space with the direct product ($\otimes$).

Say we have 2 particles each with a spin. Then the new basis for our total system will be a product of all our basis for the individual systems:
$$
\begin{align}
\ket {uu} = \ket u \otimes \ket u \\
\ket {ud} = \ket u \otimes \ket d \\
\ket {du} = \ket d \otimes \ket u \\
\ket {dd} = \ket d \otimes \ket d \\
\end{align}
$$
The direct product is not commutative so $\ket u \otimes \ket d \not = \ket d \otimes \ket u$.
Another property of the direct product is it can be used to generate new operators that act on our new vector space:
$$
\begin{align}
A \otimes B = C
\end{align}
$$
These operators act on our vectors like so:
$$
\begin{align}
( A \otimes  B)(\ket a \otimes \ket b) &= (A\ket a) \otimes (B \ket b)
\end{align}
$$
Thus our individual operators only act on their individual vector spaces.

Further, because we are doing linear algebra it surprises nobody that the direct product is linear:
$$
\begin{align}
\ket u \otimes (a\ket v + b\ket w) &= a\ket u \otimes \ket v + b \ket u \otimes \ket w\\
\end{align}
$$
## An example
Say that we have a system of two particles both with a spin that have an wave function of:
$$
\begin{align}
\ket \psi = \frac{1}{\sqrt 2}(\ket u - \ket d) \otimes (\ket u) \\
\end{align}
$$
Find $\braket {\sigma_z \otimes \sigma_x}$
$$
\begin{align}
\braket {\sigma_z \otimes \sigma_x} &= \braket{\psi | \sigma_z \otimes \sigma_x | \psi} \\
&= \bra \psi \frac{1}{\sqrt 2}(\sigma_z \otimes \sigma_x)([\ket u - \ket d] \otimes \ket u) \\
&= \bra \psi \frac{1}{\sqrt 2}(\sigma_z[\ket u - \ket d]) \otimes \sigma_x\ket u) \\
&= \frac{1}{\sqrt 2} \bra \psi (\ket u + \ket d) \otimes \ket d) \\
&= \frac{1}{2} (\bra u - \bra d)\otimes(\bra u) (\ket u + \ket d) \otimes \ket d) \\
&= \frac{1}{2} (\bra u - \bra d)(\ket u + \ket d)\otimes \braket{u|d}\\
&= \frac{1}{2} [\braket{u|u} + \braket{u | d} - \braket {d | u} - \braket{d | d}] \otimes 0\\
&= 0 \\
\end{align}
$$

