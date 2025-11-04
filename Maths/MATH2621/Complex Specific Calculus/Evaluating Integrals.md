
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
