## Using CIF
Assume that $\Gamma$ is a circle around the origin with radius 3 and $F$ is a holomorphic function on the ball of radius $\pi$
### $z^2 - 1$
$$
\begin{align}
\int_\Gamma \frac{f(z)}{z^2 - 1} dz &=
\frac{1}{2}\int_\Gamma \frac{f(z)}{z - 1} dz  - \frac{1}{2} \int_\Gamma \frac{f(z)}{z + 1}\\
&= \frac{1}{2} 2\pi if(1) - \frac{1}{2}2\pi i f(-1) \\
&= \pi i (f(1) - f(-1))
\end{align}
$$
### $(z - 1)^2$
$$
\begin{align}
\int_\Gamma \frac{f(z)}{(z-1)^2} dz &= 1!2\pi i f'(1)\\
&= 2 \pi i f'(1)
\end{align}
$$
### $(z^2 - 1)^2$
$$
\begin{align}
\int_\Gamma \frac{f(z)}{(z^2 - 1)^2} dz &= \frac{1}{4}\left[\int_\Gamma \frac{f(z)}{(z - 1)^2} dz - \int_\Gamma\frac{f(z)}{z-1}dz + \int_\Gamma\frac{f(z)}{(z+1)^2} + \int_\Gamma \frac{f(z)}{z + 1}\right] \\
&= \frac{1}{4} \left[ 1!2\pi i f'(1) - 2\pi i f(1) + 1! 2 \pi if(-1) + 2\pi i f(-1)\right] \\
&= \frac{\pi i}{2} \left[f'(1) - f(1) + f(-1) + f(-1)\right] \\
\end{align}
$$
## Real integrals
### Simple paramaterisations
Evaluate:
$$
\begin{align}
\int_{-\pi}^\pi \frac{\cos(\theta)}{5 - 4\cos(\theta)} dz
\end{align}
$$
Solution:
$$
\begin{align}
\int_{-\pi}^\pi \frac{\cos(\theta)}{5 - 4\cos(\theta)} dz &= 1/2\int_{-\pi}^\pi \frac{e^{i\theta} + e^{-i\theta}}{5 - 4 (e^{i\theta} + e^{-i\theta}) / 2} dz \\
&= \frac{1}{2}\int_{-\pi}^\pi \frac{e^{i\theta} + e^{-i\theta}}{5e^{i\theta} - 2 (e^{2i\theta} + 1)} e^{i\theta} dz \\
\text{Let } \gamma(\theta) = e^{i\theta}&: \theta \in [-\pi, \pi] \\
&= \frac{1}{2i}\int_\gamma \frac{z + z^{-1}}{5z - 2 (z^2 + 1)} dz \\
&= \frac{1}{2i}\int_\gamma \frac{z^2 + 1}{5z^2 - 2 z^3 + 2z} dz \\
&= \frac{1}{2i}\int_\gamma \frac{z^2 + 1}{z(5z - 2 z^2 + 2)} dz \\
&= \frac{1}{2i}\int_\gamma \frac{z^2 + 1}{z(5z - 2 z^2 + 2)} dz \\
\end{align}
$$
### Limits of contours
In the following problems we will define the contour of a semicircle of radius $R$. After that we will show that the contribution that the real line has to the contour dominates all other lines as $R \rightarrow \infty$ thus evaluating the real integral with contour integral techniques

#### $\int_{-\infty}^\infty \frac{1}{x^4 + 1}$
Evaluate:
$$
\begin{align}
I &= \int_{-\infty}^\infty \frac{1}{x^4 + 1} dx \\
\end{align}
$$
Sol:
First we will extend out real integral into the complex plane by defining $f(z) = \frac{1}{z^4 + 1}$.

Notice that the roots of $z^4 + 1$ and therefore the poles of $f(z)$ are all at points with $|z| = 1$.

With this knowledge we define the contour integral
$$
\begin{align}
\int_\Gamma \frac{1}{z^4 + 1}dz
\end{align}
$$
where $\Gamma$ is the upper half semicircle in the complex plane with radius $R > 1$.

We then can use the Residue theorem to evaluate this integral as
$$
\begin{align}
\int_\Gamma \frac{1}{z^4 + 1}dz &= 2\pi i \left[\text{Res}\left(f, \frac{1 + i}{\sqrt2}\right) + \text{Res}\left(f, \frac{-1 + i}{\sqrt2}\right)\right] \\
&= 2\pi i \left[ \right]
\end{align}
$$
<% tp.file.cursor(2) %>