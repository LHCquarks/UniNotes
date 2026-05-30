This page details the solution to the Schrodinger equation when $V(x) = \frac{1}{2}kx^2$ 
## Motivation
In classical mechanics the **simple harmonic oscillator** comes up everywhere. Some example are:
- A spring: $F = -kx \rightarrow V(x) = \frac{1}{2} k x^2$ 
- Very good approximation to the pendulum: $F = -mg\sin\theta \approx -mg\theta \rightarrow V(\theta) = \frac{1}{2}mg \theta^2$ 
Further, if we are in a minimum of $V(x)$ then expanding $V(x)$ as a Taylor series we get:
$$
\begin{align}
V(x) &= V(x_0) + V'(x_0) (x - x_0) + \frac{1}{2} V''(x_0)(x - x_0)^2 + \dots\\
&\approx V(x_0) + \frac{1}{2}V''(x_0) (x - x_0)^2
\end{align}
$$
Thus if the minimum is at $x_0 = 0$ and noting that constant potential just correlates to a phase difference we get:
$$
\begin{align}
V(x) &\approx  \frac{1}{2}V''(0)x^2
\end{align}
$$
This is just the harmonic oscillator formula thus it is a good approximation for most functions where $V(x)$ is at a minimum.

The classical solution to these equations are sinusoidal and have a frequency $\omega$.
It works out that we get the relationship $k = m\omega^2$ and thus from here on out we will write
$$
\begin{align}
V(x) &= \frac{1}{2}kx^2\\
&= \frac{1}{2}m\omega^2 x^2
\end{align}
$$
## Algebraic method
We can now write the Hamiltonian as
$$
\begin{align}
\hat H &= -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V \\
&= \left(\frac{1}{2m} \hat p^2 + \frac{1}{2} m\omega^2\hat x^2 \right) \\
&= \frac{1}{2m}\left(\hat p^2 +  (m\omega \hat x)^2 \right)\\
\end{align}
$$
Our goal is to now factorize this expression however, because linear operators do not generally commute we will need to do some funny business.
We can define the the two operators:
$$
\begin{align}
a_- &= \frac{1}{\sqrt{2\hbar m\omega}}(i\hat p + m\omega \hat x) \\
a_+ &= \frac{1}{\sqrt{2\hbar m\omega}}(-i\hat p + m\omega \hat x) \\
\end{align}
$$
then we get:
$$
\begin{align}
a_-a_+ &= \frac{1}{2\hbar m \omega} (i\hat p + m\omega \hat x)(-i\hat p + m\omega \hat x) \\
&= \frac{1}{2\hbar m \omega} (\hat p^2 + i\hat p m\omega \hat x - m\omega \hat xi\hat p + (m\omega \hat x)^2) \\
&= \frac{1}{2\hbar m \omega} (\hat p^2 + im\omega(\hat p \hat x - \hat x \hat p) + (m\omega \hat x)^2) \\
&= \frac{1}{2\hbar m \omega} (\hat p^2 + (m\omega \hat x)^2) + \frac{1}{2\hbar m \omega} im\omega[\hat p, \hat x]  \\
&= \frac{1}{\hbar \omega} \hat H + \frac{1}{2\hbar m \omega} im\omega (-i\hbar)  \\
&= \frac{1}{\hbar \omega} \hat H + \frac{1}{2}  \\
\end{align}
$$
And so
$$
\begin{align}
\hat H &= \hbar \omega \left(a_- a_+ - \frac{1}{2}\right)
\end{align}
$$
Similarly:
$$
\begin{align}
a_+ a_- &= \frac{1}{\hbar \omega} \hat H - \frac{1}{2}
\end{align}
$$

Now we also get
$$
\begin{align}
[a_-, a_+] &= a_- a_+ - a_+ a_- \\
&= \frac{1}{\hbar \omega} \hat H + \frac{1}{2} - \left(\frac{1}{\hbar \omega} - \frac{1}{2}\right)\\
&= \frac{1}{2} + \frac{1}{2} \\
&= 1
\end{align}
$$
Finally, also notice that $a_- = (a_+)^\dagger$.
### Maths aside
Suppose that we have an operator $a$ and $[a, a^\dagger] = 1$. Now construct the operator $N = a^\dagger a$.

Find the eigenvalues and eigenvectors of $N$:

Take the eigenvector $\ket \psi$ and it's eigenvalue $\lambda$ so that:
$$
\begin{align}
N\ket \psi = a^\dagger a \ket \psi= \lambda \ket \psi
\end{align}
$$
Now define the new vector $\ket \phi = a^\dagger \ket\psi$ and inspect it's relation to $N$:
$$
\begin{align}
N\ket\phi &= a^\dagger a a^\dagger \ket \psi \\
&= a^\dagger(a a^\dagger - a^\dagger a + a^\dagger a)\ket \psi \\
&= a^\dagger([a, a^\dagger] + a^\dagger a)\ket \psi \\
&= a^\dagger(\hat I + a^\dagger a)\ket \psi \\
&= a^\dagger(1 + \lambda)\ket \psi \\
&= (1 + \lambda)\ket \phi \\
\end{align}
$$
So $a^\dagger\ket \psi$ is also an eigenvector of $N$ with a eigenvalue of $(\lambda + 1)$.
We can do a similar thing with $a\ket \psi$ to get that it is also an eigenvector of $N$ with a eigenvalue of $(\lambda - 1)$ .

This is really cool because given one $\ket \psi$ we can generate infinite eigenvectors. It can further be proven that $\lambda \in \mathbb Z_{\ge 0}$ and thus to find the first eigenvector we solve the equation
$$
\begin{align}
a\ket {\psi_0}  &= \ket 0
\end{align}
$$
We then generate all the other vectors by:
$$
\begin{align}
\ket {\psi_n} &= \left(a^\dagger\right)^n \ket {\psi_0}
\end{align}
$$
### Solving for the ground state
If $\ket \psi$ is an eigenvector of $a_+a_-$ then we get:
$$
\begin{align}
\hat H \ket \psi &= \hbar \omega \left(a_-a_+ - \frac{1}{2} \right) \ket \psi \\
&= \hbar \omega \left(\lambda - \frac{1}{2}\right)\ket \psi
\end{align}
$$
Thus $\ket \psi$ is an eigenvector of $\hat H$.
Solving the equation
$$
\begin{align}
a_- \ket{\psi_0} &= \ket 0 \\
\frac{1}{\sqrt{2\hbar m\omega}}(i\hat p + m\omega \hat x) \psi_0 &= 0 \\
0 &= i\hat p \psi_0 + m\omega \hat x\psi_0 \\
\hbar \frac{d \psi_0}{d x}&= -m\omega x\psi_0 \\
\hbar \frac{d \psi_0}{\psi_0}&= -m\omega x dx\\
\hbar \ln(\psi_0) &= -\frac{m\omega}{2}x^2 + C \\
\psi_0 &= \exp\left(-\frac{m\omega}{2\hbar}x^2 + C\right) \\
\psi_0 &= A\exp\left(-\frac{m\omega}{2\hbar}x^2 \right) \\
\end{align}
$$
This is the Gaussian! Very cool.
Then to recover our other bounded functions we just need to apply $a_+$ so our solutions are:
$$
\begin{align}
\ket {\psi_n} &= (a_+)^n A_n \exp\left(-\frac{m\omega}{2\hbar}x^2\right)
\end{align}
$$
where $A_n$ is found with the normalization condition and is actually $A_n = 1/\sqrt{n!}$.

To find the energy of our states first we find the energy of $\ket {\psi_0}$:
$$
\begin{align}
\hat H \ket {\psi_0} &= \hbar \omega\left(a_+a_- \ket {\psi_0} + \frac{1}{2}\right) \\
&= \hbar \omega\left(0 + \frac{1}{2}\right) \\
&= \frac{\hbar \omega}{2}
\end{align}
$$
Then the energy of $\ket {\psi_n}$ is:
$$
\begin{align}
E_n &= \hbar \omega\left(n + \frac{1}{2}\right)
\end{align}
$$
