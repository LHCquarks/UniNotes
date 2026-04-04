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

This difference between operators is extremely important and is called the **Comutator** and is written like $[\hat\Lambda, \hat\Omega] = \hat\Lambda\hat\Omega - \hat\Omega\hat\Lambda$.