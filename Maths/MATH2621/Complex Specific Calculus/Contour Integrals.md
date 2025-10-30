## Curves in $\mathbb C$
A curve in $\mathbb C$ is defined much the same as in $\mathbb R^2$: a curve $t \rightarrow (\gamma_1(t), \gamma_2(t))$ is replaced with the curve $t \rightarrow \gamma_1(t) + i\gamma_2(t)$. 
The definitions of **simple** and **closed** curves are almost identical along with **joins**, **reverse curves**, **reparametrisations** and **orientations**

If $f$ is a holomorphic function and $\alpha$ is a curve in the complex plane, then
$$
\begin{align}
\frac{d}{dt}f(\alpha(t)) = f'(\alpha(t)) \alpha'(t)
\end{align}
$$
by the chain rule.
## Contours
A contour is the analogue of a **path** but in the complex plane.
It is defined as:

an oriented range of a (not necessarily simple) peicewise smooth curve in the complex plane
## Integral of a parameterized complex function
If we have a complex function given by $f(t): [a, b] \rightarrow \mathbb C$ we can decompose $f$ into two real valued functions $f(t) = u(t) + iv(t)$ which we can integrate by ignoring the complex numbers as such:
$$
\begin{align}
\int_a^b f(t) dt = \int_a^b u(t) + iv(t) dt = \int_a^b u(t) dt + i\int_a^b v(t)dt
\end{align}
$$
## Contour integrals
A contour integral is a line integral but in the complex plane and is defined as such:
$$
\begin{align}
\int_\gamma f(z) dz = \int_a^b f(\gamma(t))\gamma'(t)dt
\end{align}
$$
Instead of writing $\gamma(t)$ we can write $z(t)$ which gives us the formula:
$$
\begin{align}
\int_\gamma f(z)dz = \int_a^b f(z(t))\frac{dz}{dt}dt
\end{align}
$$
Note that in a sense $dz = \frac{dz}{dt}dt$ by the chain rule
### Properties
Similar to line integrals, contour integrals are:
- **Linear**
- **Irrespective of parametrisation**
- **Additive for joins**
- **Dependent on orientation**
- **Size can be estimated by $M\text{ Length}(\gamma)$**





$$
\begin{align}
f(w) = \frac{1}{2\pi} \int_0^{2\pi} f(w+re^{i\theta})d\theta
\end{align}
$$
