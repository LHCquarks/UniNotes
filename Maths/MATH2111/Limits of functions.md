## Definition
Take $b \in \mathbb R^n$, $\Omega \subseteq \mathbb R^m$, $a$ as a limit point of $\Omega$ and $f: \Omega \rightarrow \mathbb R^n$. It is said that $f(x)$ converges to $b$ as $x$ approaches $a$ written as $f(x) \rightarrow b$ when $x \rightarrow a$ if $\forall \epsilon > 0$ there exists a $\delta$ such that for all $x \in \Omega$
$$
\begin{align}
0 < d(x, a) < \delta \implies d(f(x), b) < \epsilon
\end{align}
$$

In English this is, if you create a ball in the output space of my function $f$ centered at $b$ then no matter the radius of that ball I can find a ball in my input space centered at $a$ such that all points in my ball map into points in your ball (except maybe the point at $a$).

## Limit of components
If you have a function $f(x) = (f_1(x), f_2(x), ..., f_n(x))$ then $f(x) \rightarrow b$ as $x \rightarrow a$ if and only if $f_i(x) \rightarrow b_i$ as $x \rightarrow a$ for all $1 \le i \le n$ 

## Limit along sequences
Take a function $f(x)$. Then $\lim_{x \rightarrow a} f(x) = b$ if and only if for every sequence $\{x_k\}_{k = 1}^\infty$ who's limit is $a$, we get $\lim_{k \rightarrow \infty} f(x_k) = b$.
Whilst this is not useful in proving the existence or value of a limit it can be used to show simple **counterexamples**



