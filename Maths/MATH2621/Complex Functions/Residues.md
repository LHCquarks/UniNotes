Suppose that the function $f$ has an isolated singularity at $z_0$ then:
- $f \in \text H(\text B^\circ (z_0, r))$ 
- $f$ has a Laurent series around $z_0$
- The residue of $f$ is the coefficient in front of the $(z - z_0)^{-1}$ term
We write this residue of $f$ at $z_0$ as $\text{Res}(f, z_0)$

Further, we get that for a holomorphic function with finitely many residues at $z_0, z_1, ... z_k$ and a inside a simple contour $\Gamma$ then:
$$
\begin{align}
\int_\Gamma f(z) dz &= 2\pi i\sum_{n=0}^k \text{Res}(f, z_n)
\end{align}
$$

## Other ways of finding residue
### Limit of derivative
Take a function $f$ which has a <span style="color:DodgerBlue">pole of order N</span>. Then we can write
$$
\begin{align}
f(z) &= c_{-N}(z - z_0)^{-N} + c_{1-N} (z- z_0) ^{1- N} + ... \\
& \ \ \ \ \ c_{-1} (z - z_0)^{-1} + c_0 (z- z_0)^0 + ... \\
(z- z_0)^N f(z) &= c_{-N} (z - z_0)^0 + c_{N-1} (z- z_0)^1 + ... \\
& \ \ \ \ \ c_{-1} (z - z_0)^{N - 1} + c_0 (z- z_0)^N + ... \\
\frac{d^N}{dz^N}((z- z_0)^N f(z)) &= (N- 1)! c_{-1}(z- z_0)^0 + ... \\
\lim_{z \rightarrow z_0} \frac{d^N}{dz^N}(z- z_0)^N f(z) &= (N - 1)! c_{-1} \\
\implies \text{Res}(f, z_0) &= \frac{1}{(N-1)!}\lim_{z \rightarrow z_0} \frac{d^N}{dz^N}(z- z_0)^N f(z)
\end{align}
$$

## Examples
Find
$$
\begin{align}
\int_\Gamma \frac{\alpha_1}{z - a} + \frac{\beta_1}{z - b} + \frac{\beta_2}{(z - b)^2} dz
\end{align}
$$
for $\Gamma$ that contains $a, b$

We get that
$$
\begin{align}
\int_\Gamma \frac{\alpha_1}{z - a} + \frac{\beta_1}{z - b} + \frac{\beta_2}{(z - b)^2} dz &= 2\pi i \sum_{n=0}^k \text{Res}(f, z_n) \\
&= 2\pi i (\alpha_1 + \beta_1)\\
\end{align}
$$
