## Semi-Classical
- $\lambda = \frac{h}{p}$
- $E = hf$
## Maths formulas
- Inner Prod
	- $\braket{u | v} = \braket{v | u}^*$
	- $|\braket{u|v}|^2 \le \braket{u|u} \braket{v|v}$
	- $\braket{u | v} = \pmatrix{u_1^* & u_2^* & \dots} \pmatrix{v_1 \\ v_2 \\ \vdots}$
	- $\braket{\Psi | \Phi} = \int_{-\infty}^\infty \Psi^*(t)\Phi(t)dt$ 
- Fourier Transform:
	- $\mathcal F(\omega) = \frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty f(x) e^{-i\omega x} dx$
	- $f(x) = \frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty \mathcal F(\omega) e^{i\omega x} d\omega$
	- $f(x) = e^{-\frac{1}{2}x^2} \rightarrow \mathcal F(\omega) = e^{-\frac{1}{2}\omega^2}$
	- $f(x) = \begin{cases}1 & |x| \le 1/2 \\ 0 & |x| > 1/2 \end{cases} \rightarrow \mathcal F(\omega) = \frac{1}{\sqrt{2\pi}} \frac{\sin(\frac{\omega}{2})}{\frac{\omega}{2}}$
	- $f(x) = \cos(x) \rightarrow \mathcal F(\omega) = \sqrt{2\pi} \frac{1}{2}[\delta(\omega - 1) + \delta(\omega + 1)]$
	- $f(ax) \rightarrow \frac{1}{|a|} \mathcal F\left(\frac{\omega}{a}\right)$
	- $\frac{d}{dx}f(x) \rightarrow i\omega\mathcal F(\omega)$
- $\sigma^2 = \braket{\Omega^2} - \braket{\Omega}^2$
## QM formulas
- $P(\omega) = |\braket{\omega | \Psi}|^2$
- $|\braket{\Psi | \Psi}|^2 = 1$
- $i\hbar \frac{\partial \Psi}{\partial t} = \hat H \Psi$
- $\hat p = -i\hbar \frac{\partial}{\partial x} \rightarrow \hat p = \hbar \omega$ 
- $\hat x = x \rightarrow \hat x = i\frac{\partial}{\partial \omega}$
- $\hat H = \frac{\hat p^2}{2m} + V(x) = -\frac{\hbar^2}{2m}\frac{\partial^2}{\partial x^2} + V(x)$
- $\hat \sigma_x = \pmatrix{0 & 1 \\ 1 & 0}$, $\hat \sigma_y = \pmatrix{0 & -i \\ i & 0}$, $\hat \sigma_z = \pmatrix{1 & 0 \\ 0 & -1}$
- $\hat H \ket \psi = E \ket \psi$, $\phi(t) = e^{-iE_i t/\hbar}$, $\Psi(x,t) = \psi(x) \phi(t)$ 
- $\sigma_A^2\sigma_B^2 \ge \left(\frac{1}{2i} [\hat A, \hat B]\right)^2$
- $[\hat x, \hat p] = i\hbar$
## Solutions to SE
### Infinite square well
$$
\begin{align}
\psi_n(x) &= \sqrt{\frac{2}{a}}\sin\left(\frac{n\pi}{a}x\right) \\
E_n &= \frac{\hbar^2n^2\pi^2}{2ma^2}
\end{align}
$$
### Finite square well
$$
\begin{align}
\psi(x) &= 
\begin{cases}
Ce^{\beta x} & x < -a \\
A\sin(kx) + B\cos(kx) & -a \le x \le a \\
De^{-\beta x} & a < x
\end{cases} \\
\beta^2 &= \frac{2m(V_0 - E)}{\hbar^2}
\end{align}
$$
### Simple Harmonic Oscillator
$$
\begin{align}
a_- &= \frac{1}{\sqrt{2\hbar m\omega}}(i\hat p + m\omega \hat x) \\
a_+ &= \frac{1}{\sqrt{2\hbar m\omega}}(-i\hat p + m\omega \hat x) \\
\ket {\psi_n} &= (a_+)^n A_n \exp\left(-\frac{m\omega}{2\hbar}x^2\right) \\
A_n &= 1 / \sqrt{n!} \\
E_n &= \hbar \omega\left(n + \frac{1}{2}\right)\\
\end{align}
$$
### Delta Potential
Bounded:
$$
\begin{align}
\psi(x) &= \frac{\sqrt{m \alpha}}{\hbar}\exp\left(-\frac{m\alpha|x|}{\hbar^2}\right) \\
E &= -\frac{m\alpha^2}{2\hbar^2}
\end{align}
$$
Scattering:
$$
\begin{align}
\psi(x) &= \cases{Ae^{ikx} + B e^{-ikx} & x < 0 \\ Ce^{ikx} & x > 0} \\
r &= \frac{B}{A} = \frac{i\beta}{1 - i\beta}, t= \frac{C}{A}= \frac{1}{1 - i \beta} \\
R &= \left|\frac{B}{A}\right|^2 = \frac{\beta^2}{1 + \beta^2} \\
T &= \left|\frac{C}{A}\right|^2 = \frac{1}{1 + \beta^2} \\
\beta &= \frac{m\alpha}{\hbar^2 k}, k = \frac{\sqrt{2mE}}{\hbar}
\end{align}
$$
