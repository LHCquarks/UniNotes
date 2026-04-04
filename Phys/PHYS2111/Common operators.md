Bellow is listed some common operators and their physical intuition:
## $\hat P$
$\hat P$ is the momentum operator and is given by $-i\hbar \frac{d}{dx}$ in position space and transforms into $\hbar k$ in Fourier space.
## $\hat x$
$\hat x$ is the position operator and is given by $x$ in position space.
## $\hat H$
$\hat H$ is the Hamiltonian operator and takes many forms depending on the question.
It most commonly takes the form $\hat H = \frac{\hat p^2}{2m} + V(x)$ but can also take on forms like $\hat H = -\mu_bB\sigma_z$
## $\hat \sigma$
$\hat \sigma$ is the generalized spin operator and encodes all the spin operators for measuring spin along any axis.
It is given by $\hat \sigma = \pmatrix {\hat \sigma_x \\ \hat \sigma_y \\ \hat \sigma_z}$. When dotted with a 3 vector in the specific direction you want to measure it will return an operator for measuring spin in that direction.

Here the operators $\hat \sigma_x, \hat \sigma_y, \hat \sigma_z$ are the Pauli spin matrices given by:
$$
\begin{align}
\hat \sigma_x &= \pmatrix{0 & 1 \\ 1 & 0} \\
\hat \sigma_y &= \pmatrix{0 & -i \\ i & 0} \\
\hat \sigma_z &= \pmatrix{1 & 0 \\ 0 & -1} \\
\end{align}
$$
An example of using them is bellow:
Say I wanted to measure the spin of a particle in the $\hat v = \pmatrix{1/\sqrt3 \\ 1/\sqrt3 \\ 1/\sqrt3}$ direction. Then:
$$
\begin{align}
\sigma_{\hat v} &= \hat \sigma \cdot \hat v \\
&= \frac{1}{\sqrt 3} \pmatrix{0 & 1 \\ 1 & 0} + \frac{1}{\sqrt 3} \pmatrix{0 & -i \\ i & \ 0}  + \frac{1}{\sqrt 3} \pmatrix{1 & \  0 \\ 0 & -1}\\
&= \frac{1}{\sqrt 3} \pmatrix{\ \ \ 1 & 1 - i\\ 1 + i &\  -1} 
\end{align}
$$

