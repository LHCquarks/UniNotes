The Laplace transform takes a function and splits it up into it's exponential parts.

We say that a function $f: [0, \infty) \rightarrow \mathbb C$ is **exponential type** $A$ if there exists a constant $C$ such that
$$
\begin{align}
|f(t)| \le Ce^{At}\ \ \ \  \forall t\in [0, \infty)\\
\end{align}
$$
and exponential type $A+$ if it is **exponential type** $A + \epsilon$  for all $\epsilon \in \mathbb R^+$

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
Just like last but $a = 0$ so:
$$
\begin{align}
\mathcal L(p(t)) &= \sum_{k=0}^Kc_k \frac{k!}{z^{k+1}}\\
\end{align}
$$
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

## Differential equations
Take the equation:
$$
\begin{align}
\frac{d^2u}{dt^2} - 2\frac{du}{dt} + u &= t \\
\text{Take the Laplace of both sides} \\
\mathcal L(u'') - 2\mathcal L(u') + \mathcal L(u) &= \frac{1}{s} \\
s^2\mathcal L(u) - u'(0) - zu(0) - 2s\mathcal L(u) + u(0) + \mathcal L(u) &= \frac{1}{s^2} \\
\text{Let } u(0) = u'(0) &= 0 \\
s^2\mathcal L(u) - 2s\mathcal L(u) + \mathcal L(u) = \frac{1}{s^2} \\
\mathcal L(u) = \frac{1}{s^2 (s^2 - 2s + 1)} \\
\mathcal L(u) = \frac{1}{s^2 (s^2 - 2s + 1)} \\
\end{align}
$$

Take the 1d wave equation
$$
\begin{align}
\frac{\partial^2 u}{\partial x^2} &= \frac{\partial^2 u}{\partial t^2}
\end{align}
$$
also take the initial conditions:
$$
\begin{align}
u(x, 0) = \frac{\partial u}{\partial t}(x, 0) = 0\\
u(0, t) = f(t) \text{ where } f(t) = 0 : \\
\end{align}
$$
taking the laplace transform with respect to t we get
$$
\begin{align}
\frac{\partial^2 \mathcal L u}{\partial x^2} &= s^2 \mathcal L u \\
\mathcal L u(z, s) &= A(s) e^{sx} + B(s)e^{-sx} \\
\end{align}
$$
To keep our string bounded we assume that $A(s) = 0$ so
$$
\begin{align}
B(s) = \mathcal L u(0,s) = \mathcal L f(s) \\
\implies u(z, t) = f(t - x) \\
\end{align}
$$
## Convolutions
The convolution of f and g denoted as $f *g$ is:
$$
\begin{align}
f * g(t) = \int_0^t f(s) g(t-s)ds
\end{align}
$$
We get the properties:
$$
\begin{align}
f*(ag + bh) &= af*g + bf*h\\
f*g &= g*f \\
\mathcal L (f*g) &= \mathcal Lf \mathcal Lg
\end{align}
$$
Take the equation:
$$
\begin{align}
u(t) = t^2 - \frac{2}{3} \int_0^t (t-s)^3 u(s)ds
\end{align}
$$
Notice this is the convolution:
$$
\begin{align}
u(t) &= t^2 - \frac{2}{3}t^3 *u(t)\\
\mathcal Lu &= \frac{2}{z^3} - \frac{4}{z^4} \mathcal Lu \\
\mathcal Lu &= \frac{2z}{z^4 + 4} \\
u &= \sum_{j=0}^k \text{Res}(\frac{2z}{z^4 + 1} e^{zt}, z_j) \\
u &= \sum_{j=0}^k \text{Res}(\frac{2z}{z^4 + 1} e^{zt}, z_j) \\
u &= \sinh t\sin t \text{ Trust me bro}\\
\end{align}
$$
