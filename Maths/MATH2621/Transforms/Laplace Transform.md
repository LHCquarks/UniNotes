The Laplace transform takes a function and splits it up into it's exponential parts.

We say that a function is exponential type $A$ if there exists a constant $C$ such that
$$
\begin{align}
|f(t)| \le Ce^{At}\\
\end{align}
$$
and exponential type $A+$ if there exists a constant $C$ such that
$$
\begin{align}
|f(t)| \le Ce^{(A + \epsilon)t}
\end{align}
$$

Linear combinations of exponentials of type A and B makes a new function of type $\max\{A, B\}$ and multiples are of type $A + B$A

## Deffinition
The Laplace transform is defined for functions $f: [0, \infty) \rightarrow \mathbb C$ and is defined as:
$$
\begin{align}
\mathcal L_f(z) = \int_0^\infty f(t) e^{-zt}dt\\
\end{align}
$$
## Properties
### Linearity
The Laplace transform is linear:
$$
\begin{align}
\mathcal L(af + bg) = a\mathcal L(f) + b \mathcal L(g)
\end{align}
$$
### Transforms of key functions
#### Transform of polynomial times exp
$$
\begin{align}
\mathcal L(p(t)e^{at}) &= \int_0^\infty \sum_{k=0}^Kc_kt^ke^{(a - z)t} dt \\
&= \sum_{k=0}^Kc_k \int_0^\infty t^ke^{(a - z)t} dt \\
&= \sum_{k=0}^Kc_k \frac{k!}{(z-a)^{k+1}}\\
\end{align}
$$
#### Transform of exp
This is just the last but $p(t) = 1$ so
$$
\begin{align}
\mathcal L(e^{at}) &= \frac{0!}{(z-a)^{0+1}}\\
&= \frac{1}{z - a} \\
\end{align}
$$
#### Transform of polynomial
### Derivative
The derivative of a Laplace transform is 
$$
\begin{align}
\frac{d}{dz}\mathcal L(f(t)) &= \mathcal L(-tg(t)) \\
\end{align}
$$
We also get that
$$
\begin{align}
\mathcal L(f') &= z\mathcal L(f) - f(0)\\
\end{align}
$$

### Translation
$$
\begin{align}
g(t) &= e^{-at}f(t)\\
\mathcal Lg(z) &= \mathcal L f(z+a) \\
\end{align}
$$
### Der
$$
\begin{align}
g(t) &= tf(t) \\
\mathcal L g(z) &= -\frac{d}{dz}\mathcal Lf(z)
\end{align}
$$
## Inversion formula
To invert the Laplace transform we can use the formula
$$
\begin{align}
f(t) = \lim_{R \rightarrow \infty} \frac{1}{2\pi i} \int_\lambda \mathcal Lf(z)e^{tz}dz
\end{align}
$$
where $\lambda$ is the line segment from $\sigma - iR$ to $\sigma + iR$ and $\sigma \in(A, \infty)$ 

Further, if $|\mathcal Lf(t)| \le M|z|^{-k}$ then
$$
\begin{align}
f(t) = \sum_{j = 1}^n \text{Res}(\mathcal L f(z) e^{zt}, z = a_j)
\end{align}
$$
where $a_j$ are all the problem points