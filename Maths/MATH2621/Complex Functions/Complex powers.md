To define complex powers we make use of exponentials and logarithms.
For some $z, \alpha \in \mathbb C$ we write the **multi valued** function
$$
\begin{align}
z^\alpha = \exp(\alpha\log(z))
\end{align}
$$
Or for the principle branch we write
$$
\begin{align}
\text{PV } z^\alpha = \exp(\alpha\text{Log}(z))
\end{align}
$$
## Derivative
The complex power is differentiable on $\mathbb C \backslash (-\infty, 0]$ with the derivative
$$
\begin{align}
\frac{d}{dz}(\text{PV }z^\alpha) &= \alpha\frac{\text{PV }z^\alpha}{z}
\end{align}
$$
## Example
Find the principle value of $i^i$:
$$
\begin{align}
\text{PV } i^i &= \exp(i\text{Log}(i)) \\
&= \exp(i(i\text{Arg}(i) + \ln|i|)) \\
&= \exp(i(i\frac{\pi}{2} + \ln(1))) \\
&= \exp(i(i\frac{\pi}{2})) \\
&= \exp(-\frac{\pi}{2})) = e^{-\pi/2}\\
\end{align}
$$
