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
### Recap of 1-d case
For a function $f: [a, b]\rightarrow \mathbb R$  we can partition the interval $[a, b]$ into $n + 1$ points giving $\mathcal P = \{x_0, x_1, \dots , x_n\}$ where $a = x_0 < x_1 < \dots < x_n = b$. 
We then define the sums
$$
\begin{align}
\underline S_{\mathcal P} (f) &= \sum_{k = 1}^n (x_n - x_{n-1}) \underline f_k \\
\overline S_{\mathcal P} (f) &= \sum_{k = 1}^n (x_n - x_{n-1}) \overline f_k
\end{align}
$$
where:
$$
\begin{align}
\underline f_k &= \inf_{x \in [x_{n-1}, x_n]} f(x) \\
\overline f_k &= \sup_{x \in [x_{n-1}, x_n]} f(x) \\
\end{align}
$$
If there exists a real number $I$ such that $\underline S_{\mathcal P} (f) \le I \le \overline S_{\mathcal P}(f)$  for every partition $\mathcal P$ of $[a, b]$ we say that $f$ is Riemann integrable and we call $I$ the definite integral of $f$ from $a$ to $b$ and we write it like this:
$$
\begin{align}
I &= \int_a^b f(x) dx
\end{align}
$$
### Definition
Let $D\subset R^n$ be a rectangular region:
$$
\begin{align}
D &= [a_1, b_1] \times [a_2, b_2] \times \dots \times [a_n, b_n]
\end{align}
$$
We then take partitions $\mathcal P_i$ of $[a_i, b_i]$ for all $1 \le i \le n$ and consider the partition $\mathcal P$ induced by $\mathcal P_0, \mathcal P_1, \dots, \mathcal P_n$ which subdivides the region $D$ into rectangles

Then as we did in the 1-d case we define the sums:
$$
\begin{align}
\underline S_{\mathcal P} (f) &= \sum_{R \in \mathcal P} \underline f_R \text{Vol}(R) \\
\overline S_{\mathcal P} (f) &= \sum_{R \in \mathcal P} \overline f_R \text{Vol}(R) \\
\end{align}
$$
We then say that $f$ is Riemann integrable on $D$ if for every $\varepsilon > 0$  there exists a partition $\mathcal P$ of $D$ such that
$$
\begin{align}
\overline S_{\mathcal P} (f) - \underline S_{\mathcal P} (f) < \varepsilon
\end{align}
$$
The value that both $\overline S_{\mathcal P} (f), \underline S_{\mathcal P} (f)$ approach as $\varepsilon \rightarrow 0$ is the integral of $f$ over the region $D$ denoted by:
$$
\begin{align}
\idotsint_D f(x_0, \dots, x_n) dx_0 \dots dx_n
\end{align}
$$
Where there are $n$ integral signs.
Sometimes it is also written as
$$
\begin{align}
\int_D f(\vec x) d\vec x
\end{align}
$$
For the 2-d case there is also the notation
$$
\begin{align}
\int_D f dA
\end{align}
$$
And likewise for the 3-d case:
$$
\begin{align}
\int_D f dV
\end{align}
$$
### Properties
Multi-dimensional integrals have the following properties:
- Linearity: $\int_D [af(\vec x) \pm bg(\vec x)] d\vec x = a\int_D f(\vec x)d\vec x \pm b\int_D g(\vec x) d\vec x$ 
- Monotonicity: if $f(x) \le g(x)$ on $D$ then $\int_D f(\vec x) d\vec x \le \int_D g(\vec x) d\vec x$
- $\left|\int_D f(\vec x) d\vec x\right| \le \int_D |f(\vec x) |d\vec x$
### When is $f$ not Riemann Integrable?
$f$ is not integrable 