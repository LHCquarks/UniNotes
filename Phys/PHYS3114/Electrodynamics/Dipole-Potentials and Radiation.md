Assume we have a time varying perfect electric dipole at the origin $\vec p(t)$.

We will start by finding our $\varphi$ and $\vec A$ using our Green's function:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi \epsilon_0} \int_{\mathbb R^3} \frac{\rho(\vec r', t_r)}{R} dr'
\end{align}
$$
We can now use the same principles used when deriving the multipole expansion in PHYS2114 to get:
$$
\begin{align}
\frac{1}{R} &= \frac{1}{r}\sum_{n=0}^\infty \left(\frac{r'}{r}\right)^nP_n(\cos\alpha)
\end{align}
$$
and using this our $\varphi(\vec r, t)$ goes to
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0}\sum_{n = 0}^\infty\frac{1}{r^{n + 1}}  \int_{\mathbb R^3}(r')^n P_n(\cos \alpha) \rho(\vec r', t_r) dr'
\end{align}
$$
Now, because we assumed this was a electric mono-pole no matter the time we have that all but the $n=1$ terms vanish leaving us with:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0} \frac{1}{r^2} \int_{\mathbb R^3} r' \cos\alpha \rho(\vec r', t_r) dr' \\
 &= \frac{1}{4\pi\epsilon_0} \frac{1}{r^2} \int_{\mathbb R^3} \hat r \cdot \vec r' \rho(\vec r', t_r) dr' \\
 &= \frac{1}{4\pi\epsilon_0} \frac{1}{r^2} \hat r \cdot\int_{\mathbb R^3}  \vec r' \rho(\vec r', t_r) dr' \\
\end{align}
$$
On top of this we can then Taylor expand $\rho(\vec r', t_r)$ in the $t'$ slot around $t_c = t - |r| / c$ like so:
$$
\begin{align}
\rho(\vec r', t_r) &= \rho(\vec r', t_c) + \frac{1}{2}\rho(\vec r', t_c) (t_r - t_c) + \dots \\
&\approx \rho(\vec r', t_c) + \frac{t - |r' - r| / c - t + |r| / c}{2} \rho(\vec r', t_c) \\
&\approx \rho(\vec r', t_c) + \frac{|r| - |r' - r|}{c} \rho(\vec r', t_c) \\

\end{align}
$$
<% tp.file.cursor(2) %>
