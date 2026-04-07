## Leibniz Rule
Suppose that $D = [c, d] \times [a, b]$ and that $f(x, t)$ is some real valued function defined on some open set $U \subseteq \mathbb R^2$ which contains $D$. Also assume that $f$ is continuous on $U$ along with $\frac{\partial f}{\partial x}$ existing.
Then for $x \in [c, d]$:
$$
\begin{align}
\frac{\partial}{\partial x} \int_a^b f(x, t) dt &= \int_a^b \frac{\partial f}{\partial x}(x, t) dt
\end{align}
$$
### Applications
$$
\begin{align}
I(a) &= \int_0^1 x \sin(ax) dx \\
&= \int_0^1 \frac{\partial}{\partial a} (\sin(ax)) dx \\
&= \frac{\partial}{\partial a} \int_0^1  \sin(ax) dx \\
&= \frac{\partial}{\partial a} \left[\frac{-\cos(ax)}{a}\right]_0^1 \\
&= \frac{\partial}{\partial a} \left[\frac{-\cos(a)}{a} + \frac{1}{a}\right] \\
&= \frac{\partial}{\partial a} \left[\frac{1-\cos(a)}{a} \right] \\
&= \frac{\sin(a)}{a} - \frac{1- \cos(a)}{a^2} \\
&= \frac{a\sin(a) + \cos(a) - 1}{a^2} \\
\end{align}
$$
$$
\begin{align}
I(a, b) &= \int_0^\infty \frac{e^{-ax} - e^{-bx}}{x} dx \\
\frac{\partial I}{\partial b} &= \int_0^\infty \frac{\partial}{\partial b} \left[\frac{e^{-ax} - e^{-bx}}{x}\right] dx \\
&= \int_0^\infty \left[-\frac{- xe^{-bx}}{x}\right] dx \\
&= \int_0^\infty e^{-bx} dx \\
&=  \left[\frac{e^{-bx}}{-b}\right]_0^\infty \\
&=  \left[0 + \frac{1}{b}\right] \\
&=  \frac{1}{b} \\
I(a, b) &= \int \frac{1}{b} db \\
I(a, b) &= - \frac{1}{b^2} + C(a) \\
\text{Let } b=a \\
I(a, a) &= C(a) - \frac{1}{a^2} = \int_0^\infty \frac{e^{-ax} - e^{-ax}}{x} dx \\
C(a) - \frac{1}{a^2} &= \int_0^\infty 0 dx \\
C(a) - \frac{1}{a^2} &= 0 \\
C(a) &= \frac{1}{a^2} \\
\implies I(a, b) &= \frac{1}{a^2} - \frac{1}{b^2}
\end{align}
$$
### Generalization
We can generalize the Leibniz rule to also work when the bounds involve our variable as such:

Suppose $D = [c, d] \times [a, b]$ and $f: U \rightarrow \mathbb R$  where $D \subseteq U \subseteq \mathbb R^2$ and $U$ is open. Also assume that $f(x, t)$ is continuous on $U$ and and $\frac{\partial f}{\partial x}$ exists. Then for $x \in [c, d]$:
$$
\begin{align}
\frac{d}{dx} \left( \int_{a(x)}^{b(x)}f(x, t) dt\right) &= f(x, b(x)) b'(x) - f(x, a(x)) a'(x) + \int_{a(x)}^{b(x)} \frac{\partial f}{\partial x} (x, t) dt
\end{align}
$$
## n-dimensional integrals
### Definition
