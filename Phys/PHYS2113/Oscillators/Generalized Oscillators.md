## What is an oscillator
Given a set of equations of motion, if they can be written as
$$
\begin{align}
\sum_{i}M_{i} \ddot q_i &= \sum_j K_j q_j
\end{align}
$$
Then the system is an **oscillator** and we can use some powerful theory on it.

Given a potential, if we are at a local minimum then we can use Taylor expansions to get that
$$
\begin{align}
U(q) \approx U(0) + \sum_i\partial_i U(0) q_i + \frac{1}{2}\sum_{j, k} \partial_j\partial_kU(0)q_jq_k
\end{align}
$$
And because we are at a local minima $\partial_i U(0) = 0$ and $U(0)$ is a constant so we can ignore it. Therefore
$$
\begin{align}
U(q) \approx \frac{1}{2}\sum_{j, k} K_{j, k} q_j q_k
\end{align}
$$
Further more assuming that the kinetic energy takes on a similar form:
$$
\begin{align}
T(\dot q) = \frac{1}{2}\sum_{i, j} M_{i, j} \dot q_i \dot q_j
\end{align}
$$

and thus solving the EL equations gives
$$
\begin{align}
\frac{\partial \mathcal L}{\partial q_i} &= \frac{d}{dt}\left(\frac{\partial \mathcal L}{\partial \dot q_i}\right) \\
-\sum_k K_{i, k}q_k &= \sum_{j} M_{i, j}\ddot q_j
\end{align}
$$
## Solving Oscillator problems
Given the equations of motion
$$
\begin{align}
\sum_{j} M_{i, j}\ddot q_j &= -\sum_k K_{i, k}q_k
\end{align}
$$
we can define the vector $\vec q = (q_1, q_2, \dots, q_n)$ and thus rewrite all these equations of motion into one big vector problem:
$$
\begin{align}
M \vec{\ddot q} &= -K\vec q
\end{align}
$$
Taking the ansatz $q_i(t) = A_ie^{i\omega t}$ we get that $\vec{\ddot q} = -\omega^2 \vec q$ and so we can rewrite our matrix equation as
$$
\begin{align}
-\omega^2M\vec q &= -K\vec q \\
 0 &= K\vec q - \omega^2M\vec q \\
 0 &= \left(K - \omega^2M\right)\vec q \\
\end{align}
$$
This is just an eigenvector equation that we can solve. In this case $\omega^2$ is the eigenvalue whist $\vec q$ is the corresponding eigenvector. Once these eigenvectors are obtained the general equations of motion are just a linear sum of the eigenvectors. ie if $\vec a_i$ are the eigenvectors with $\omega_i^2$ eigenvalues then the equations of motion are

$$
\begin{align}
q(t) &= \sum_{i} A_i \vec a_i e^{i\omega_it}
\end{align}
$$
## Carts with springs attached
Consider a frictionless plane with two carts of mass $m_1, m_2$ on top. These carts are then connected to the walls and to themselves by springs with spring constants $k_1, k_2, k_3$ as shown in the diagram:
![[Pasted image 20260717120335.png]]
Let the coordinates $x_1, x_2$ refer to the displacements of $m_1, m_2$ from their equilibrium respectively.

Then $T = \frac{1}{2}(m_1 \dot x_1^2 + m_2 \dot x_2^2)$ and  $U = \frac{1}{2}(k_1 x_1^2 + k_2 (x_2 - x_1)^2 + k_3 x_2^2)$.

Thus our equations of motion are
$$
\begin{align}
m_1\ddot x_1 &= -k_1 x_1 - k_2(x_1 - x_2) \\
m_2\ddot x_2 &= -k_2 x_2 - k_2(x_2 - x_1) \\
\end{align}
$$
Which we can simplify into 
$$
\begin{align}
m_1\ddot x_1 &= -\left[(k_1+ k_2) x_1 + k_2x_2) \right]\\
m_2\ddot x_2 &= -\left[(k_1+ k_2) x_2 + k_1x_1) \right]\\
\end{align}
$$
Then defining the matrices
$$
\begin{align}
M &= \pmatrix{m_1 & \ 0 \\ \ 0 & m_2} \\
K &= \pmatrix{k_1 + k_2 & \ \ \ \ \ k_2 \\ \ \ \ \ \ k_1 & k_1 + k_2}
\end{align}
$$
we have the equation
$$
\begin{align}
M\ddot x &= -Kx
\end{align}
$$
This system is thus an oscillator and we just have to find the eigenvalues.
To make this easier on the calculations we will set $k = k_1 = k_2$ and $m = m_1 = m_2$ and thus:
$$
\begin{align}
(K - \omega^2M) x &= 0 \\
\left |\matrix{2k - \omega^2 m & k \\ k & 2k - \omega^2 m}\right| &= 0 \\
(2k - \omega^2 m)^2 - k^2 &= 0 \\
(2k - \omega^2 m - k) (2k - \omega^2 m + k) &= 0 \\
(k - \omega^2 m) (3k - \omega^2 m) &= 0 \\
\omega_1^2 = \frac{k}{m}, \omega_2^2 = \frac{3k}{m}
\end{align}
$$
Then finding the eigenvectors becomes a problem of row reducing
$$
\begin{align}
&\left(
\begin{array}{cc|c}
2k - \frac{k}{m}m & k & 0 \\
k & 2k-\frac{k}{m}m & 0
\end{array}
\right) \\
\rightarrow
&\left(
\begin{array}{cc|c}
2k - k & k & 0 \\
k & 2k- k& 0
\end{array}
\right) \\
\rightarrow
&\left(
\begin{array}{cc|c}
1 & 1 & 0 \\
1 & 1 & 0
\end{array}
\right) \\

\rightarrow
&\left(
\begin{array}{cc|c}
1 & 1 & 0 \\
0 & 0 & 0
\end{array}
\right) \\
\vec a_1 &= \pmatrix{\ \ 1 \\ -1}
\end{align}
$$
$$
\begin{align}
&\left(
\begin{array}{cc|c}
2k - \frac{3k}{m}m & k & 0 \\
k & 2k-\frac{3k}{m}m & 0
\end{array}
\right) \\
\rightarrow
&\left(
\begin{array}{cc|c}
2k - 3k & k & 0 \\
k & 2k- 3k& 0
\end{array}
\right) \\
\rightarrow
&\left(
\begin{array}{cc|c}
-1 & 1 & 0 \\
1 & -1 & 0
\end{array}
\right) \\

\rightarrow
&\left(
\begin{array}{cc|c}
-1 & 1 & 0 \\
0 & 0 & 0
\end{array}
\right) \\
\vec a_2 &= \pmatrix{1 \\ 1}
\end{align}
$$
This means that the general equation of motion of the system is
$$
\begin{align}
\pmatrix{x_1(t) \\ x_2(t)} &= A_1 \vec a_1 e^{i\omega_1 t} + A_2 \vec a_2 e^{i \omega_2 t} \\
&= A_1 \pmatrix{\ \ 1 \\ -1} e^{i\sqrt{k / m} \ t} + A_2 \pmatrix{1 \\ 1} e^{i \sqrt{3k/ m}\  t} \\
&= \pmatrix{
\ \ \ A_1 e^{i\sqrt{k / m}\ t} + A_2e^{i \sqrt{3k / m}\ t} \\
-A_1 e^{i\sqrt{k / m}\ t} +  A_2e^{i \sqrt{3k / m}\ t} \\
}
\end{align}
$$
Where $A_1, A_2$ are complex coefficients given by the initial conditions.
## Normal modes and normal coordinates
The eigenvectors of our above equations correspond to pure modes of oscillation for our system and so are called **normal modes**. Because they only have one frequency present they are very simple to work with and so as such we can change our coordinate system around it.

Defining $\zeta_i(t)$ as the unique numbers so that $\vec q(t) = \sum_i \zeta_i(t) \vec a_i$  then we have that $\zeta_i(t) = A_ie^{i\omega_i t}$. Notice how we only depend on one frequency here? In a sense these are then the simplest coordinates we can express our system with, however, the physical meaning of these coordinates does get obscured a bit.