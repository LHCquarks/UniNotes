Suppose that $f(z) = z^n$ were $n \ge 2$ then $f$ is not one-to-one.

We can then restrict $f$ to a region $\Omega$ such that $\Omega = \{ z \in \mathbb C: |Arg(z)| < \pi/n\}.$ Within this domain $f$ becomes one-to-one and we can define an inverse function for it.
![[zto5.png]]
This particular branch is the principle branch and all other branches are just *constant multiples* of each other where the multiplying factors are the nth roots of unity.

The principle value inverse function is defined as:
$$
\begin{align}
\text{PV } z^{1/n} = 
\begin{cases}
\exp(\text{Log}(z)/n) = |z|^{1/n}e^{i\text{Arg}(z)/n} & \text{if } z \not = 0\\ 
0  & \text{if } {z = 0}
\end{cases}
\end{align}
$$
## Differentiable
This function is differentiable in $\mathbb C \\ (-\infty, 0]$ where it's derivative is:
$$
\begin{align}
\frac{\text{PV } z^{1/n}}{nz}
\end{align}
$$
This is because the end points of the defined wedge collapse onto one another at the negative real line.

## Roots of polynomials
Take the root of the polynomial $(z^2 - 1)^{1/2}$. Two ways to define this function are:
$$
\begin{align}
\text{PV } (z^2 - 1)^{1/2} = 
\begin{cases}
|z^2 - 1|^{1/2}e^{i\text{Arg}(z^2 - 1) /2} &\text{when } z \not= \pm1 \\
0 &\text{when } z = \pm1
\end{cases}
\end{align}
$$
or since $z^2 - 1 = (z - 1)(z + 1)$:
$$
\begin{align}
\text{PV } (z^2 - 1)^{1/2} = 
\begin{cases}
|z^2 - 1|^{1/2}e^{i\text{Arg}(z - 1) /2} e^{i\text{Arg}(z+1)/2} &\text{when } z \not= \pm1 \\
0 &\text{when } z = \pm1
\end{cases}
\end{align}
$$
