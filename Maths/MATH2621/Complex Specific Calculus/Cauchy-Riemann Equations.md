## Overview
For any function $f$, it is differentiable on an *open* set $\Omega$ if and only if the Cauchy-Riemann equations hold:
If $f(x + iy) = u(x,y) + iv(x, y)$ then
$$
\begin{align}
\frac{\partial u}{\partial x} &= \frac{\partial v}{\partial y} \\
\frac{\partial u}{\partial y} &= -\frac{\partial v}{\partial x} \\
\end{align}
$$
and all the above partial derivatives are continuous.
On top of this we get the identity that:
$$
\begin{align}
f'(x+iy) = \frac{\partial u}{\partial x}(x, y) + i \frac{\partial v}{\partial x} (x, y) \\
f'(x+iy) = \frac{\partial v}{\partial y}(x, y) - i \frac{\partial u}{\partial y} (x, y)
\end{align}
$$
## Proof
By the definition of the complex limit, if the limit $\lim_{w \rightarrow 0} q(w)$ exists:
$$
\begin{align}
\lim_{\underset{w \in \mathbb R}{w \rightarrow 0}} q(w) =
\lim_{w \rightarrow 0} q(w) =
\lim_{\underset{w \in i\mathbb R}{w \rightarrow 0}} q(w) \tag{1}
\end{align}
$$
This fact, along with the ability to decompose complex functions into real functions like so:
$$
\begin{align}
f(x+iy) = u(x,y) + iv(x, y) \tag{2}
\end{align}
$$
tells us that if $f$ is differentiable then the following equations hold:
$$
\begin{align}
 \frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x} &= \frac{\partial f}{\partial x}  \tag{2}\\
&= \frac{df}{dz} \frac{\partial z}{\partial x}  \\
&= \frac{df}{dz}\frac{\partial}{\partial x}(x+iy) \\
&= \frac{df}{dz} \\
\end{align}
$$
and
$$
\begin{align}
\frac{\partial u}{\partial y} + i\frac{\partial v}{\partial y} &= \frac{\partial f}{\partial y}  \tag{2}\\
&= \frac{df}{dz} \frac{\partial z}{\partial y}  \\
&= \frac{df}{dz}\frac{\partial}{\partial y}(x+iy)  \\
&= i \frac{df}{dz} \\
\implies \frac{df}{dz} &= - i \frac{\partial u}{\partial y} + \frac{\partial v}{\partial y}
\end{align}
$$
Combining these two equations we get that
$$
\begin{align}
\frac{df}{dz} &= \frac{df}{dy} \\
\implies \frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x} &= \frac{\partial v}{\partial y} - i \frac{\partial u}{\partial y} \\
\implies \frac{\partial u}{\partial x} &= \frac{\partial v}{\partial y} \\
\implies \frac{\partial v}{\partial x} &= -\frac{\partial u}{\partial y} \\
\end{align}
$$
## Lin alg
If we say that $f'(z) = b + ic$ then we get that
$$
\begin{align}
f'(z) (h + ik) &=
\begin{pmatrix}
b & -c \\
c & b
\end{pmatrix}
\begin{pmatrix}
h \\ k
\end{pmatrix}

= 
\begin{pmatrix}
\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y} \\ \frac{\partial v}{\partial x} & \frac{\partial v}{ \partial y}
\end{pmatrix}
\begin{pmatrix}
h \\ k
\end{pmatrix}
\end{align}
$$
## Consequences of CR equations
### Constant functions
If $f$ is differentiable on a *domain* $\Omega$ in $\mathbb{C}$ then if any of the following are true:
- If $f' = 0$ in $\Omega$
- If $|f|$ is constant in $\Omega$
- If either $\text{Re}(f)$ or $\text{Im}(f)$ is constant
then $f$ is a constant function.

## Polar coordinates
If we have a differentiable function $f$ and let $z = r_0 e^{i\theta_0}$ then
$$
\begin{align}
\frac{\partial u}{\partial \theta} &= - r_0\frac{\partial v}{\partial r} \\
\frac{\partial v}{\partial \theta} &= r_0 \frac{\partial u}{\partial r} \\
\end{align}
$$
and
$$
\begin{align}
f'(z_0) &= e^{-i\theta_0} \left(\frac{\partial u}{\partial r}(r_0, \theta_0)+ i\frac{\partial v}{\partial r}(r_0, \theta_0)\right) \\
&= -\frac{ie^{i\theta_0}}{r_0}\left(\frac{\partial u}{\partial \theta}(r_0, \theta_0) + i \frac{\partial v}{\partial \theta}(r_0, \theta_0)\right)
\end{align}
$$

