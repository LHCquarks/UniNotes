Given a local (does not extend to infinity) charge distribution we can produce a sort of Taylor expansion for the voltage called the **Multi-pole Expansion**. To do this we start with the general formula for the voltage at any point:
$$
\begin{align}
V &= \frac{1}{4\pi \epsilon_0} \int \frac{1}{\mathscr r} \rho(\vec r') d\tau'
\end{align}
$$
If we then think about the relationship between $\vec r'$ and $\vec r$ we can use the law of cosines to get
![[screenshot-2026-06-30_07-42-35.png]]
$$
\begin{align}
\mathscr r^2 &= r^2 + (r')^2 2rr'\cos(\alpha)
\end{align}
$$
We can then simplify this as
$$
\begin{align}
\mathscr r^2 &= r^2\left[1 + \left(\frac{r'}{r}\right)^2 - 2\left(\frac{r'}{r}\right)\cos\alpha\right] \\
\mathscr r&= r\sqrt{1 + \varepsilon} \\
\frac{1}{\mathscr r} &= \frac{1}{r}(1 + \varepsilon)^{-1/2}
\end{align}
$$
where $\varepsilon = \left(\frac{r'}{r}\right) \left(\frac{r'}{r} - 2\cos \alpha\right)$. We can then use the Taylor expansion of $(1 + \varepsilon)^{-1/2}$ to get
$$
\begin{align}
\frac{1}{\mathscr r} &= \frac{1}{r}\left(1 - \frac{1}{2}\varepsilon + \frac{3}{8}\varepsilon^2 - \frac{5}{16}\varepsilon^3 + \dots \right) \\
\frac{1}{\mathscr r} &= \frac{1}{r}\left[
1 
- \frac{1}{2}\left(\frac{r'}{r}\right) \left(\frac{r'}{r} - 2\cos \alpha\right)
+ \frac{3}{8}\left(\frac{r'}{r}\right)^2 \left(\frac{r'}{r} - 2\cos \alpha\right)^2 + \dots \right] \\
\end{align}
$$
Surprisingly, if you group this expression in terms of $\frac{r'}{r}$ the coefficients of these terms is given by the Legendre polynomials $P_n(\cos \alpha)$. Thus we get:
$$
\begin{align}
\frac{1}{\mathscr r} &= \frac{1}{r}\sum_{n=0}^\infty \left(\frac{r'}{r}\right)^nP_n(\cos\alpha)
\end{align}
$$
Substituting this into our formula for voltage we get:
$$
\begin{align}
V &= \frac{1}{4\pi \epsilon_0} \int \frac{1}{r}\sum_{n=0}^\infty \left(\frac{r'}{r}\right)^nP_n(\cos\alpha) \rho(\vec r') d\tau' \\
&= \frac{1}{4\pi \epsilon_0} \sum_{n=0}^\infty  \frac{1}{r^{n + 1}} \int \left(r'\right)^nP_n(\cos\alpha) \rho(\vec r') d\tau' \\
\end{align}
$$
This is the full **Multi-pole expansion**.

The power of the multi-pole expansion is its ability to approximate fields when $r$ is large. When $r$ is large the higher order terms in the multi-pole expansion becomes negligible so it is often sufficient to take just the first non-zero term.

## Mono-pole Term
The $n = 0$ term of the multi-pole expansion is called the mono-pole term. It is given by:
$$
\begin{align}
V&= \frac{1}{4\pi \epsilon_0} \frac{1}{r} \int \rho(\vec r') d\tau' \\
&= \frac{1}{4\pi \epsilon_0} \frac{1}{r} Q\\
&= \frac{1}{4\pi \epsilon_0} \frac{Q}{r} \\
\end{align}
$$
This says that any charge distribution behaves equivalently to a point charge with the same total charge centered at the origin in the limit as $r$ gets large.
## Di-pole Term
The $n = 1$ term of the multi-pole expansion is called the di-pole term. This term is given by:
$$
\begin{align}
V&= \frac{1}{4\pi \epsilon_0} \frac{1}{r^{2}} \int r' \cos\alpha \rho(\vec r') d\tau' \\
\end{align}
$$
Noting that $r' \cos \alpha = \hat r \cdot \vec r'$ we can rewrite the above expression as:
$$
\begin{align}
V&= \frac{1}{4\pi \epsilon_0} \frac{1}{r^{2}} \int \hat r \cdot \vec r' \rho(\vec r') d\tau' \\
&= \frac{1}{4\pi \epsilon_0} \frac{1}{r^{2}} \hat r \cdot \int \vec r' \rho(\vec r') d\tau' \\
&= \frac{1}{4\pi \epsilon_0} \frac{\hat r \cdot \vec p}{r^{2}} \\
\end{align}
$$
Where $\vec p = \int \vec r' \rho(\vec r') d\tau'$. This $\vec p$ is called the dipole moment of the distribution and is a fairly important object as it describes entire neutral charge distributions very effectively. 

For discrete charge distributions the definition of $\vec p$ unsurprisingly simplifies to $\vec p = \sum_{i = 1}^n q_i\vec r'_i$.
For equal and opposite charges this simplifies further to $\vec p = q\vec d$ where $\vec d$ is the vector that points from the negative to positive charge.

Whilst this is known as the dipole term it does not actually describe physical dipoles (where each end of the dipole are separated by a distance) as those have higher order correcting terms but this term does perfectly describe a theoretical dipole