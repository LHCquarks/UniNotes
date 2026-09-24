**Fraunhofer diffraction** or **far-field diffraction** is an approximation for the diffraction pattern on a far away screen. We start with a plain wave incident on a small apature which iluminates a far away detector:
![[Pasted image 20260925073614.png]]
For this derivation we will ignore the time component of these waves and ignore the normalisation constant $\mathscr A$ as they have no effect on our final solution.

The apature takes the incident plane wave and modifies it by some function $f(x, y)$ giving the new wave on the apature is:
$$
\begin{align}
\phi(\vec r, t) &= f(x, y) e^{ikz} \\
&= f(x, y)
\end{align}
$$
We then get the equation of the secondary wavelets as:
$$
\begin{align}
\psi(x, y, r, \chi) &= f(x,y) \frac{e^{ikr}}{r} \kappa(\chi)
\end{align}
$$
where the bellow diagram applies:
![[Pasted image 20260925074540.png]]
The total wave on the detector is then:
$$
\begin{align}
\Phi(\zeta, \eta) &= \iint_{\text{appature}} \psi(x, y, r, \chi) dxdy \\
&= \iint f(x, y) \frac{e^{ikR}}{R} \kappa(\chi) dxdy \\
\end{align}
$$
Now, for a far away detector, $\chi$ is approximatly constant accross the integral so we can pull it out of the integral. Also we have that $R \approx R_0$ Thus we can pull out the denominator however we can not replace the phase as $ikR = 2\pi i R / \lambda = 2\pi i (R_0 / \lambda + \Delta R / \lambda)$ but $\Delta R$ is not vanishing small compared to $\lambda$.

Thus we get the slightly simpler integral
$$
\begin{align}
\Phi(\zeta, \eta) &= \frac{\kappa(\chi)}{R_0} \iint f(x, y)e^{ikR}dxdy
\end{align}
$$
We can now use pythag to get
$$
\begin{align}
R^2 &= z^2 + (\zeta - x)^2 + (\eta - y)^2 \\
R_0^2 &= \zeta^2 + \eta^2 + z^2 \\
R^2 &= R_0^2 - 2(\zeta x- \eta y) + x^2 + y^2 \\
&= R_0^2
\end{align}
$$
<% tp.file.cursor(2) %>