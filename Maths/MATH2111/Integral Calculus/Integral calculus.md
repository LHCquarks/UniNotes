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
### When is $f$ not Riemann integrable?
$f$ is not Riemann integrable when the set of discontinuities of $f$ does not have measure $0$. This essentially means that the generalized volume (Measure) of the set of discontinuities have to be zero for $f$ to be Riemann integrable.
### Integrating on non-rectangular regions
To integrate over a region $C \subset \mathbb R^n$ we take a rectangular region $D$ such that $C \subseteq D \subset \mathbb R^n$  and define the indicator function:
$$
\begin{align}
\mathbb 1_C(\vec x) = 
\begin{cases}
1 & \vec x\in C \\
0 & \text{Otherwise}
\end{cases}
\end{align}
$$
And thus our integral of $f$ becomes:
$$
\begin{align}
\int_C f(\vec x) d\vec x &= \int_D \mathbb 1_C(\vec x) f(\vec x) d\vec x
\end{align}
$$
Because $\{\vec x : \mathbb 1_C \text{ is discontinuous at } \vec x\} = \partial C$  we conclude that for a continuous $f(\vec x)$ we can integrate over $C$ iff the boundary of $C$ has measure zero

## Fubini's theorem
Let $A \subseteq \mathbb R^n$ and $B \subseteq \mathbb R^m$ be rectangular regions. Let $f: A \times B \rightarrow \mathbb R$ be Riemann integrable on $A \times B$. Then for all $x \in A$ except for possibly a set of measure zero the function
$$
\begin{align}
\vec y \rightarrow f(\vec x, \vec y)
\end{align}
$$
is Riemann integrable. Likewise for all $y\in B$ except for possibly a set of measure zero the function
$$
\begin{align}
\vec x \rightarrow f(\vec x, \vec y)
\end{align}
$$
is Riemann integrable.
Moreover:
$$
\begin{align}
\int_{A \times B} f dV &= \int_A \left(\int_B f(\vec x, \vec y) d\vec y\right) d\vec x \\
&= \int_B \left(\int_A f(\vec x, \vec y) d\vec x\right) d\vec y
\end{align}
$$
## Integrating over arbitrary regions
I feel that this is best described through examples:
![[Pasted image 20260409080504.png]]
In the above example to integrate over the region $R$ we notice that we can take vertical strips thus we can first integrate with respect to $y$ no problem. We can then build our integral like so:
$$
\begin{align}
\iint_R dA &= \int_{x_0}^{x_1} \int_{\phi_1(x)}^{\phi_2(x)} dydx
\end{align}
$$
If we were to then do the x-axis first we would have to split it into two integrals when $\phi_1(x)$ goes  up again to account for the two regions.

When we can do the first method on a region we call it **y-simple**. When we can do it with the x-axis we call it **x-simple**
## Change of variables
Given an integral what is our higher dimensional equivalent to the $u$ sub?

Say we have a region $u, v$ and we have some map $\vec r(u, v)$ that takes us from our $u, v$ world to our $x, y$ world. Then we can consider the image of a small rectangular region in $u, v$ like so:
![[Pasted image 20260415103238.png]]
Now, The area of our square originally was $dudv$ and thus the area in the $x,y$ space is $|\det(J)|dudv$. This means we get that:
$$
\begin{align}
dxdy = |\det(J)|dudv
\end{align}
$$
Thus our change of variable formula int the multivariable case is:
$$
\begin{align}
\iint_{F(A)} f(x, y) dxdy &= \iint_{A} f(F(u, v)) |\det(J)| dudv
\end{align}
$$
This also generalizes to any dimension with the bellow formula
$$
\begin{align}
\int_{F(A)} f(\vec y) d\vec y &= \int_A (f \circ F)(\vec x) |\det(J_F(\vec x))| d\vec x
\end{align}
$$
## Common substitutions
Some common substitutions include:
### Polar sub
$$
\begin{align}
x &= r\cos(\theta) \\
y &= r\sin(\theta)
\end{align}
$$
for $r > 0, \theta \in [0, 2\pi]$.
We get 
$$
\begin{align}
|\det(J)| &= 
\begin{Vmatrix}
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta} \\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta} \\
\end{Vmatrix} \\
&= 
\begin{Vmatrix}
\cos\theta & -r\sin\theta \\
\sin\theta & r\cos\theta \\
\end{Vmatrix} \\
&= |r\cos^2\theta + r \sin^2\theta| \\
&= r
\end{align}
$$
### Cylindrical coordinates
$$
\begin{align}
x &= r\cos\theta\\
y &= r\sin\theta\\
z &= z\\
\end{align}
$$
for $r > 0, \theta \in [0, 2\pi], z \in \mathbb R$.
We get
$$
\begin{align}
|\det(J)| &= 
\begin{Vmatrix}
\frac{\partial x}{\partial r} & \frac{\partial x}{\partial \theta} & \frac{\partial x}{\partial z}\\
\frac{\partial y}{\partial r} & \frac{\partial y}{\partial \theta} & \frac{\partial y}{\partial z}\\
\frac{\partial z}{\partial r} & \frac{\partial z}{\partial \theta} & \frac{\partial z}{\partial z}\\
\end{Vmatrix} \\
&= 
\begin{Vmatrix}
\cos\theta & -r\sin\theta & 0\\
\sin\theta & r\cos\theta  & 0\\
0 & 0 & 1\\
\end{Vmatrix} \\
&= |r\cos^2\theta + r \sin^2\theta| \\
&= r
\end{align}
$$
### Spherical coordinates
$$
\begin{align}
x &= \rho \cos\theta \sin\phi \\
y &= \rho \sin\theta \sin\phi \\
z &= \rho \cos\phi \\
\end{align}
$$
for $\rho > 0, \theta \in [0, 2\pi], \phi \in [0, \frac{\pi}{2}]$. In these coordinates:
- $\rho$ is the distance from the origin
- $\theta$ is the angle from the positive x-axis in the x-y plane
- $\phi$ is the angle from the positive z-axis

We get:
$$
\begin{align}
|\det(J)| &= 
\begin{Vmatrix}
\frac{\partial x}{\partial \rho} & \frac{\partial x}{\partial \theta} & \frac{\partial x}{\partial \phi}\\
\frac{\partial y}{\partial \rho} & \frac{\partial y}{\partial \theta} & \frac{\partial y}{\partial \phi}\\
\frac{\partial z}{\partial \rho} & \frac{\partial z}{\partial \theta} & \frac{\partial z}{\partial \phi}\\
\end{Vmatrix} \\
&= 
\begin{Vmatrix}
\cos\theta \sin\phi & -\rho\sin\theta\sin\phi & \rho\cos\theta\cos\phi\\
\sin\theta\sin\phi & \rho\cos\theta\sin\phi  & \rho\sin\theta\cos\phi\\
\sin\phi & 0 & -\rho\sin\phi\\
\end{Vmatrix} \\
&= |r\cos^2\theta + r \sin^2\theta| \\
&= r
\end{align}
$$