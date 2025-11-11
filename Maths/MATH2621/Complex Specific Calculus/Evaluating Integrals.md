
Assume that $\Gamma$ is a circle around the origin with radius 3 and $F$ is a holomorphic function on the ball of radius $\pi$
$$
\begin{align}
\int_\Gamma \frac{f(z)}{z^2 - 1} dz &=
\frac{1}{2}\int_\Gamma \frac{f(z)}{z - 1} dz  - \frac{1}{2} \int_\Gamma \frac{f(z)}{z + 1}\\
&= \frac{1}{2} 2\pi if(1) - \frac{1}{2}2\pi i f(-1) \\
&= \pi i (f(1) - f(-1))
\end{align}
$$
$$
\begin{align}
\int_\Gamma \frac{f(z)}{(z-1)^2} dz &= 1!2\pi i f'(1)\\
&= 2 \pi i f'(1)
\end{align}
$$
$$
\begin{align}
\int_\Gamma \frac{f(z)}{(z^2 - 1)^2} dz &= \frac{1}{4}\left[\int_\Gamma \frac{f(z)}{(z - 1)^2} dz - \int_\Gamma\frac{f(z)}{z-1}dz + \int_\Gamma\frac{f(z)}{(z+1)^2} + \int_\Gamma \frac{f(z)}{z + 1}\right] \\
&= \frac{1}{4} \left[ 1!2\pi i f'(1) - 2\pi i f(1) + 1! 2 \pi if(-1) + 2\pi i f(-1)\right] \\
&= \frac{\pi i}{2} \left[f'(1) - f(1) + f(-1) + f(-1)\right] \\
\end{align}
$$


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


Evaluate:
$$
\begin{align}
I &= \int_{-\infty}^\infty \frac{1}{x^4 + 1} dx \\
\end{align}
$$
Sol:
$$
\begin{align}
I &= \int_{-\infty}^\infty \frac{1}{(z-\omega_1)(z-\omega_2)(z-\omega_3)(z-\omega_4)} dx \\
\text{Take the contour that is the semicircle of the uper half plane with radius} \ge 1 \\
\text{By residue thrm} \\
I &= 
\end{align}
$$
<% tp.file.cursor(2) %>