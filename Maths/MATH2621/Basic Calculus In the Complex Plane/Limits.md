## Definition
Let $f$ be a complex function and $l\in\mathbb{C}$ a number.

Suppose that $z_0$ is in the **closure** of $\text{Domain}(f)$.

We call $l$ the limit of $f$ as $z \rightarrow z_0$ if for every $\epsilon \in \mathbb{R}^+$ there exists a $\delta \in \mathbb{R}^+$ such that
$$
|f(z) - l| < \epsilon
$$
provided that
$$
0 < |z - z_0| < \delta.
$$

In English:

For any ball in the output space of $f$ centered at $l$ with radius $\epsilon$ we can construct another ball of radius $\delta$ centered at $z_0$ such that any $z$ inside of the second ball will be mapped into the first ball.

We denote this as
$$
\lim_{z\rightarrow z_0} f(z) = l
$$
## Restricted Limit
The Restricted limit is like the normal limit except we only allow $z$ to be apart of a set $S$ such that $S \subseteq \text{Domain}(f)$.

This is also written as
$$
\lim_{\underset{z\in S}{z\rightarrow {z_0}}}f(z) = l
$$

### Additional property
We get the property that if $T \subseteq S \subseteq \text{Domain}(f)$ and $z_0 \in \bar T$. 
If $\lim_{\underset{z\in S}{z\rightarrow z_0}} f(z)$ exists then so does $\lim_{\underset{z\in T}{z\rightarrow z_0}} f(z)$ And they are equal
## Infinity
During this course we are sometimes allowed to refer to $\infty$ as a number under the pretense of the Riemann sphere.

Here, if we want to ask $$
\begin{align}
\lim_{z \rightarrow \infty}
\end{align}
$$
We redefine the limit as:
If for every $\epsilon$ there exists some $\delta$ such that for any $z \in \text{Domain}(f)$ with $|z| > 1/\delta$  we get that $|f(z) - l| < \epsilon$.

This simply says that for a limit as $z \rightarrow \infty$ to exist $l$ must be approached from all directions including $\infty$, $-\infty$, $\infty i$, $-\infty i$ and even $\infty (1 + i)$.

## Unifying infinity limit and normal limit

We can replace the original definition of a limit to the following:
	"For every $\epsilon \in \mathbb{R}^+$, there exists $\delta \in \mathbb{R}^+$ such that any $z \in \text{Domain}(f) \cap B^{o}(z_0, \delta)$ satisfies $f(z) \in B(l, \epsilon)$ "

And then we define the ball around infinity as such:
$$
\begin{align}
B(\infty, \delta) = B^{o}(\infty, \delta)= \{ z\in \mathbb{C}: |z| > 1/\delta \}
\end{align}
$$
## Standard limits
The following are to be taken for granted for $c, \alpha \in \mathbb{C}$
$$
\begin{align}
\lim_{z\rightarrow \alpha} c &= c \\
\lim_{z\rightarrow \infty} c &= c \\
\lim_{z\rightarrow \alpha} z-c &= \alpha - c \\
\lim_{z\rightarrow \infty} z-\alpha &= \infty \\
\lim_{z\rightarrow \alpha} \frac{1}{z - \alpha} &= \infty \\
\lim_{z\rightarrow \infty} \frac{1}{z - \alpha} &= 0 \\
\end{align}
$$
## Properties of limits
The following are common properties of limits when $c\in \mathbb{C}$:
$$
\begin{align}
\lim_{z\rightarrow z_0}cf(z) &= c \lim_{z\rightarrow z_0} f(z) \\
\lim_{z\rightarrow z_0}(f(z) + g(z)) &= \lim_{z\rightarrow z_0} f(z) +\lim_{z\rightarrow z_0} g(z)\\
\lim_{z\rightarrow z_0}(f(z)g(z)) &= (\lim_{z\rightarrow z_0} f(z))( \lim_{z\rightarrow z_0} g(z)) \\
\lim_{z\rightarrow z_0}\frac{f(z)}{g(z)} &= \frac{\lim_{z\rightarrow z_0} f(z)}{ \lim_{z\rightarrow z_0} g(z)} \\
\lim_{z \rightarrow z_0} \overline{f(z)} &= \overline{\lim_{z \rightarrow z_0} f(z)} \\
\lim_{z \rightarrow z_0} \text{Re}(f(z)) &= \text{Re} (\lim_{z \rightarrow z_0} f(z)) \\
\lim_{z \rightarrow z_0} \text{Im}(f(z)) &= \text{Im} (\lim_{z \rightarrow z_0} f(z)) \\
\lim_{z \rightarrow z_0} f(z) &= \lim_{z \rightarrow z_0} \text{Re}(f(z)) + i\lim_{z\rightarrow z_0} \text{Im}(f(z))\\
\end{align}
$$

## Lhopital's rule
LHopital's rule holds in the complex plane