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

\end{align}
$$
<% tp.file.cursor(2) %>