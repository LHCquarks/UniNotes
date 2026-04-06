## Consecutive measurements
Lets say that I have two observables, $\Omega$ and $\Lambda$. Then lets say I measure $\Omega$ putting my wave function into a state $\ket \omega$ and then I measure $\Lambda$ getting $\lambda$. Is my wave function still in $\ket \omega$?
Well this depends on the relationship between our $\Omega$ and $\Lambda$.

If $\Omega$ and $\Lambda$ share an eigenbasis then a subsequent measurement of $\Lambda$ will not disturb our state $\ket \omega$.
Denote a shared eigenvector of this basis as $\ket {\omega \lambda}$. This means that:
$$
\begin{align}
\hat \Omega \ket {\omega \lambda} &= \omega \ket{\omega \lambda} \\
\hat \Lambda \ket {\omega \lambda} &= \lambda \ket{\omega \lambda} \\
\end{align}
$$
Applying the opposite operators to both then gives
$$
\begin{align}
\hat \Lambda \hat \Omega \ket {\omega \lambda} &= \omega \lambda \ket{\omega \lambda} \\
\hat \Omega \hat \Lambda \ket {\omega \lambda} &= \omega \lambda \ket{\omega \lambda} \\
\end{align}
$$
This then means that:
$$
\begin{align}
\hat \Lambda \hat \Omega \ket {\omega \lambda} &= \hat \Omega \hat \Lambda \ket{\omega \lambda} \\
\hat \Lambda \hat \Omega \ket {\omega \lambda}  - \hat \Omega \hat \Lambda \ket{\omega \lambda} &= 0\\
\left(\hat \Lambda \hat \Omega  - \hat \Omega \hat \Lambda \right)\ket{\omega \lambda} &= 0\\
\end{align}
$$
Applying this for all vectors in the shared eigenbasis we get that
$$
\begin{align}
\hat \Lambda \hat \Omega  - \hat \Omega \hat \Lambda &= \hat 0\\
\end{align}
$$
Thus for our observables to have a shared eigenbasis and for them not to mess with each other their operators must follow the above equation otherwise they will mess with each other and we **can not** know **both** properties of the particle **simultaneously**.

This difference between operators is extremely important and is called the **Commutator** and is written like $[\hat\Lambda, \hat\Omega] = \hat\Lambda\hat\Omega - \hat\Omega\hat\Lambda$.
## The Uncertainty principle
The **generalized** uncertainty is given by John uncertain as:
$$
\begin{align}
\sigma_A^2\sigma_B^2 \ge \left(\frac{1}{2i} [\hat A, \hat B]\right)^2
\end{align}
$$
This says that that the product of the variances of two different observables is no matter what greater than or equal to the commutator between the two measurements times some constant squared.

### Heisenberg uncertainty principle
The Heisenberg uncertainty principle is just the generalized uncertainty principle applied to the $\hat x$ and $\hat p$ operators.
For this we will need to find $[\hat x, \hat p]$ which we can do be applying it to a general wave function $\Psi$
$$
\begin{align}
[\hat x, \hat p]\Psi &= x\frac{\partial \Psi}{\partial x} - \frac{\partial}{\partial x}(x\Psi) \\
&= x\frac{\partial \Psi}{\partial x} - \frac{\partial}{\partial x}2(\Psi)
\end{align}
$$
<% tp.file.cursor(2) %>


Applied to position and momentum we get the relation:
$$
\begin{align}
\sigma_x^2 \sigma_p^2 &\ge \left(\frac{1}{2i} [\hat x, \hat p]\right)^2\\
&= \left(\frac{1}{2i}\left[x(-i\hbar)\frac{\partial}{\partial x}  - \right]\right)
\end{align}
$$
<% tp.file.cursor(2) %>