In this course we define the Fourier transform of some function $f(x)$  as:
$$
\begin{align}
\mathcal F\{f\} = F(x) = \int_{-\infty}^\infty f(x)e^{-2\pi isx}dx
\end{align}
$$
and the inverse FT as:
$$
\begin{align}
\mathcal F^{-1}\{F\} = f(x) = \int_{-\infty}^\infty F(s)e^{2\pi i sx}ds
\end{align}
$$
## Theorems and properties
### double and quadruple FT
We have the following properties
$$
\begin{align}
\mathcal F\{\mathcal F\{f\}\} &= f(-x) \\
\mathcal F \{\mathcal F\{\mathcal F\{\mathcal F\{f\}\}\}\} &= f(x) \\
\end{align}
$$
### Odd and Even
We know every function $f(x)$ can be expressed in terms of an odd function $f_o(x)$ and an even function $f_e(x)$ as:
$$
\begin{align}
f(x) &= f_o(x) + f_e(x) \\
f_o(x) &= \frac{1}{2}\left[f(x) + f(-x)\right] \\
f_e(x) &= \frac{1}{2}\left[f(x) - f(-x)\right] \\
\end{align}
$$
This can then be used in our definition of the Fourier transform to get:
$$
\begin{align}
\mathcal F\{f\} &= \int_{-\infty}^\infty \left[f_o(x) + f_e(x)\right]e^{-2\pi isx} dx \\
&= \int_{-\infty}^\infty f_o(x) e^{-2\pi isx}dx + \int_{-\infty}^\infty f_e(x) e^{-2\pi isx} dx \\
&= \int_{-\infty}^\infty f_o(x) \cos(2\pi sx) dx +  i\int_{-\infty}^\infty f_o(x) \sin(2\pi sx) dx \\
&\ \ \ \ + \int_{-\infty}^\infty f_e(x) \cos(2\pi sx) dx +  i\int_{-\infty}^\infty f_e(x) \sin(2\pi sx) dx \\
 \\
\end{align}
$$
Now, the first term is odd even which is odd thus our integral from $-\infty$ to $\infty$ vanishes. Similarly, the forth term is even odd and so the integral vanishes so we get:
$$
\begin{align}
\mathcal F\{f\} &= \int_{-\infty}^\infty f_e(x)\cos(2\pi sx)dx + i\int_{-\infty}^\infty f_o(x)\sin(2\pi sx) dx
\end{align}
$$
Thus real and even functions have real even transforms and real odd functions have imaginary and odd transforms.
### Similarity theorem
Given the function $f(x)$ with a FT of $F(x)$ the Fourier transform of $f(ax)$ is:
$$
\begin{align}
\mathcal F\{f(ax)\} &= \int_{-\infty}^\infty f(ax) e^{-2\pi i sx}dx \\
\end{align}
$$
letting $u = ax$ we get $du = adx$. We also realize that if $a$ is negative our bounds swap which we can revert by taking the minus sign from $a$ thus our FT becomes:
$$
\begin{align}
\mathcal F\{f(ax)\}&= \frac{1}{|a|}\int_{-\infty}^\infty f(u) e^{-2\pi i su/a}dx \\
&=\frac{1}{|a|}F\left(\frac{s}{a}\right) \\
f(ax) &\rightarrow \frac{1}{|a|}F\left(\frac{s}{a}\right)
\end{align}
$$
### Linearity theorem
From the linearity of the integral we get the FT is linear, ie for some functions $f, g$, their FT $F, G$ and constants $\alpha, \beta$ we get:
$$
\begin{align}
\mathcal F\{\alpha f(x) + \beta g(x)\} &= \alpha F(s) + \beta G(s)
\end{align}
$$
### Shift theorem
Suppose we have a function $f$ with FT $F$ then we get:
$$
\begin{align}
\mathcal F\{f(x - a)\} &= \int_{-\infty}^\infty f(x - a) e^{-2\pi i sx} dx \\
\text{let } u &= x - a \\
\mathcal F\{f(x - a)\} &= \int_{-\infty}^\infty f(u) e^{-2\pi i s (u + a)} dx \\
&= \int_{-\infty}^\infty f(u) e^{-2\pi i s u} e^{-2\pi i s a} dx \\
&= e^{-2\pi i s a}\int_{-\infty}^\infty f(u) e^{-2\pi i s u} dx \\
&= e^{-2\pi i s a}F(s)

\end{align}
$$
### Derivative
With function $f$ that has FT of $F$ we get:
$$
\begin{align}
\mathcal F \left\{\frac{df}{dx}\right\} &= \int_{-\infty}^\infty \frac{df}{dx}e^{-2\pi isx}dx \\
&=\left[f(x)e^{-2\pi i s x}\right]_{-\infty}^\infty + 2\pi i s\int_{-\infty}^\infty f(x) e^{-2\pi isx}dx \\
&=0 + 2\pi i sF(s)\\
&=2\pi i sF(s)\\
\end{align}
$$
Assuming that $f(x)\rightarrow 0$  as $x \rightarrow \pm \infty$.
### Rayleigh theorem
We also get the property for a function $f$ and it's FT $F$:
$$
\begin{align}
\int_{-\infty}^\infty |f(x)|^2 dx &= \int_{-\infty}^{\infty}|F(s)|^2 ds
\end{align}
$$
## Transform Pairs
The following are pairs of functions that are each other's Fourier's transforms
$$
\begin{align}
e^{-\pi x^2} &\rightarrow e^{-\pi s^2} \\
\frac{\sin(\pi x)}{\pi x} & \rightarrow \Pi(s) \\
\left(\frac{\sin(\pi x)}{\pi x}\right)^2 &\rightarrow \Lambda(s) \\
1 &\rightarrow \delta(s) \\
\cos(\pi x) &\rightarrow \delta(|s| - 1/2) \\
\sin(\pi x) &\rightarrow i\frac{s}{|s|}\delta(|s| - 1/2) \\
\text{array}(x) &\rightarrow \text{array}(s)
\end{align}
$$
where:
- $\Pi(s)$ is the hat function defined by
$$
\begin{align}
\Pi(s) = \cases{1 & |s| < 1/2 \\ 0}
\end{align}
$$
- $\Lambda(s)$ is the spike function defined by
$$
\begin{align}
\Lambda(s) &= \cases{x + 1 & -1 < x < 0 \\ 1 - x & 0 < x < 1 \\ 0}
\end{align}
$$
- $\text{array}(s)$ is the array function defined by
$$
\begin{align}
\text{array}(s) &= \sum_{n \in \mathbb Z}\delta(x - n)
\end{align}
$$
## Convolutions
### Definition and Intuition
The convolution of two functions $f(x), g(x)$ is defined as 
$$
\begin{align}
(f *g)(u) &= \int_{-\infty}^\infty f(x)g(u - x)dx \\
&= (f \otimes g)(u)
\end{align}
$$
This operation represents a blending of the two functions and has applications in many areas.

The convolution is:
- **Commutative**
- **Associative**
- **Distributive**
### Use in "duplicating" functions
Lets inspect the convolution of some function $f(x)$ with the delta function. First to make things extra clear we will define the new function $g(x) = \delta(x - a)$ and thus:
$$
\begin{align}
(f*g)(u) &= \int_{-\infty}^\infty f(x) g(u  -x)dx \\
&= \int_{-\infty}^\infty f(x) \delta(u - x - a)dx \\
&= f(u - a)
\end{align}
$$
Thus the delta function shifts $f$ to an arbitrary spot so if we want our function to appear in $a_i$  spots we can just take the convolution:
$$
\begin{align}
f * \left[\sum_i\delta(x - a_i)\right] &= \sum_i f(x - a_i)
\end{align}
$$
We can also scale these functions by multiplying by some coefficients $\alpha_i$.

### Convolution theorem
The convolution theorem is about how a convolution of two functions behaves under a FT. We get the following two identities:
$$
\begin{align}
\mathcal F \{f * g\} &= \mathcal F\{f\} \cdot \mathcal F\{g\} \\
\mathcal F \{f\} *\mathcal F\{g\} &= \mathcal F\{f\cdot g\}
\end{align}
$$

