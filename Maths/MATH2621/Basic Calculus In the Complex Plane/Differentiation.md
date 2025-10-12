## Differentiability
Let $S \subseteq \mathbb{C}$ and $f: S \rightarrow \mathbb C$ a  complex function. We say $f$ is differentiable at the point $z_0 \in S$ if 
$$
\lim_{w \rightarrow 0} \frac{f(z_0 + w) - f(z_0)}{w}
$$
or equivalently
$$
\lim_{z \rightarrow z_0} \frac{f(z) - f(z_0)}{z-z_0}
$$
These above limits are called the **derivative** of $f$ at $z_0$, written as $f'(z_0)$ or $\frac{df}{dz}(z_0)$.

We say a function is differentiable if the derivative exists for all $z\in S$.

## Derivative laws
Like real numbers we get that:
$$
\begin{align}
\frac{d}{dz}(z^n) &= nz^{n-1} \\
\frac{d}{dz}(cf) &= cf' \\
\frac{d}{dz}(f + g) &= f' + g' \\
\frac{d}{dz}(fg) &= fg' + gf' \\
\frac{d}{dz}(f\circ g) &= (f' \circ g)g' \\
\end{align}
$$

## Common functions
Let $f(z) = \bar z$
$f$ is not differentiable anywhere in $\mathbb C$. Yikes!

Let $f(z) = |z|^2$
$f$ is *Only* differentiable at 0 in which case $f'(0) = 0$

## Continuity
As with real numbers if a function is differentiable then it is also continuous

## Holomorphic
If we have an *open* subset of the complex plane $\Omega \in \mathbb{C}$ and a complex function $f: \Omega \rightarrow \mathbb C$  and $f$ is differentiable then we call it **Holomorphic** or **Complex Analytic** or **Regular**.

## Derivatives of inverses
As with real calculus the derivative of an inverse function is related to the derivative of the original function as such.
If $f(z_0) = w_0$ then:
$$
\begin{align}
(f^{-1})'(w_0) = \frac{1}{f'(z_0)}
\end{align}
$$
