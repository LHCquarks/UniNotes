## Definition
The Fourier Transform of a **locally integrable** function $f: \mathbb R \rightarrow \mathbb C$ is the function $\hat{f}: \mathbb R \rightarrow \mathbb C$ such that:
$$
\begin{align}
\hat{f}(\xi) &= \int_{-\infty}^\infty f(x)e^{-ix\xi}dx\\
\end{align}
$$
## Riemann-Lebesque Lemma 
If $f$ is **locally integrable** then $\hat{f}$ is bounded and continuous and vanishes at infinity

## Inversion formula
If $f$ and $\hat f$ are both reasonably nice, then
$$
\begin{align}
f(x) = \frac{1}{2\pi} \int_{-\infty}^\infty \hat f(\xi) e^{ix\xi}d\xi
\end{align}
$$
Note that this is effectively the Fourier Transform again except with a constant and without the minus sign. In fact if the Fourier Transform is denoted by $\mathcal F$ then:
$$
\begin{align}
\mathcal F^{-1}(\hat f) = \frac{1}{2\pi}\mathcal F(\hat f)(-x)
\end{align}
$$

