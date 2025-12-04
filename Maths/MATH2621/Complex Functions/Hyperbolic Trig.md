## Definition
We define
$$
\begin{align}
\cosh (z) &= \frac{e^z + e^{-z}}{2} = \sum_{n\in \mathbb N} \frac{z^{2n}}{(2n)!}\\
\sinh (z) &= \frac{e^z - e^{-z}}{2} = \sum_{n\in \mathbb N} \frac{z^{2n+1}}{(2n+1)!} \\
\end{align}
$$
## Properties
We get that:
$$
\begin{align}
\cosh(-z) &= \cosh(z) \tag{1} \\
\sinh(-z) &= -\sinh(z) \tag{2} \\
\cosh(z + 2\pi ik) &= \cosh(z) \tag{3} \\
\sinh(z + 2\pi ik) &= \sinh(z) \tag{4} \\
\cosh(x + y) &= \cosh(x)\cosh(y) + \sinh(x)\sinh(y) \tag {5} \\
\sinh(x + y) &= \cosh(x)\sinh(y) + \sinh(x)\cosh(y) \tag {6} \\
\cosh^2(z) - \sinh^2(z) &= 1 \tag {7} \\
\cosh(x + iy) &= \cosh(x)\cos(y) + i\sinh(x)\sin(y) \tag {8}\\
\sinh(x + iy) &= \sinh(x)\cos(y) + i\cosh(x)\sin(y) \tag {9}\\
\end{align}
$$
and that:
$$
\begin{align}
\cosh(ix) &= \cos(x) \\
\sinh(ix) &= i\sin(x)
\end{align}
$$
## Derivatives
We get the identities:
$$
\begin{align}
\frac{d}{dx}\cosh(x) &= \sinh(x) \tag{1} \\
\frac{d}{dx}\sinh(x) &= \cosh(x) \tag{2}
\end{align}
$$
## Inverses
### $\cosh(z)$
$$
\begin{align}
\cosh(z) &= w \\
\frac{1}{2}(\exp(z) + \exp(-z)) &= w \\
\exp(z) + \exp(-z) &= 2w \\
\exp(z) - 2w &= -\exp(-z) \\
\exp^2(z) - 2w\exp(z) &= - 1 \\
(\exp(z) - w)^2 &= w^2 - 1 \\
\exp(z) - w &= \pm \sqrt{w^2 - 1} \\
\exp(z) &= \pm \sqrt{w^2 - 1} + w\\
z &= \log(\pm \sqrt{w^2 - 1} + w) \\
z &= \text{Log}(\pm \sqrt{w^2 - 1} + w) + 2\pi i k\\
z &= \ln|\pm \sqrt{w^2 - 1} + w| + i\text{Arg}(w \pm \sqrt{w^2 - 1}) + 2\pi i k\\
\text{Note: } (w + \sqrt{w^2 - 1})(w - \sqrt{w^2 - 1}) &= 1 \\
\implies \frac{1}{w+\sqrt{w^2 - 1}} &= w - \sqrt{w^2 - 1} \\
\implies \text{Log}(w \pm \sqrt{w^2 - 1}) &= \pm \text{Log}(w + \sqrt{w^2 - 1}) + 2 \pi i \\
\implies z &= \pm \text{Log}(w + \sqrt{w^2 - 1}) + 2 \pi i k \\
\text{Or for multi valued log and sqrt: } \\
\implies z &= \log(w + \sqrt{w^2 - 1})\\
\end{align}
$$
This is continuous and differentiable for all $w \not \in (-\infty, 1]$ where:
$$
\begin{align}
\frac{d}{dw}(\cosh^{-1}(w)) &= \frac{1}{\sqrt{w+1} \sqrt{w-1}}
\end{align}
$$


### $\sinh(z)$
With basically the same proof as above we get:
$$
\begin{align}
\sinh(z) &= w \\
z &= \text{Log}(w \pm \sqrt{w^2 + 1}) \\
\text{or: } \\
z &= \text{Log}(w + \sqrt{w^2 + 1}) \text{ and} \\
z &= -\text{Log}(w + \sqrt{w^2 + 1}) + 2i\pi
\end{align}
$$
This is continuous and differentiable for all $w \not = it$ for $t \in \mathbb R$ with $|t| \ge 1$.
Where
$$
\begin{align}
\frac{d}{dw}(\sinh^{-1}(w)) = \frac{1}{\sqrt{w^2 + 1}}
\end{align}
$$
with all functions the principle kind.
