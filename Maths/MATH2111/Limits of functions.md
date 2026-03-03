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

## Continuity of functions
Suppose that $\Omega \subseteq \mathbb R^n$, $a \in \mathbb R^n$, and $f: \Omega \rightarrow \mathbb R^m$. then $f$ is **continuous** at $a$ if $\lim_{x \rightarrow a} f(x) = f(a)$

or in quantifiers:
$$
\begin{align}
\forall \epsilon > 0 \ \ \ \exists\delta > 0 \ \ \ \forall x \in \Omega \cap B(a, \delta) \ \ \ f(x) \in B(f(a), \epsilon)
\end{align}
$$
### Continuity of components
A function $f(x)$ is continuous if and only if $f_i(x)$ are continuous

## Elementary functions
We say that $f$  is elementary if it is:
- constant
- maps $x$ to any of $x_i, \cos x_i, \sin x_i, \text{exp } x_i$
- is an inverse of an elementary function
- is a sum or product of elementary functions
- is a composition of elementary functions

All elementary functions are continuous
## Continuity of preimages
Suppose that $\Omega \subseteq \mathbb R^n$  is open and $f: \Omega \rightarrow \mathbb R^m$. Then $f$ is continuous if and only if $f^{-1}(U)$ is open for every open $U \subseteq \mathbb R^m$

Similarly, if $f: \mathbb R^n \rightarrow \mathbb R^m$. Then $f$ is continuous if and only if $f^{-1}(\Omega)$ is a closed subset of $\mathbb R^n$  for every closed $\Omega \in \mathbb R^m$

## Path connected sets
A set $\Omega \subseteq \mathbb R^n$ is a path-connected set if for every $x, y \in \Omega$, there is a continuous function $\varphi: [0, 1] \rightarrow \Omega$ such that $\varphi(0) = x$ and $\varphi(1) = y$
### Union
If $\Omega_1, \Omega_2$ are path-connected with $\Omega_1 \cap \Omega_2 \not = \varnothing$  then $\Omega_1 \cup \Omega_2$ is path connected
### Generalized intermediate value theorem
If $\Omega \subseteq \mathbb R^n$ is path-connected and $f: \Omega \rightarrow \mathbb R^n$ is continuous, then $f(\Omega)$ is path connected.
## Bounded sets
A bounded set is a set $\Omega$ if there exists a $M$ that for all elements $x \in \Omega$:
$$
\begin{align}
d(x, 0) \le M
\end{align}
$$
## Compact sets
A compact set is a set that is both **closed** and **bounded**
### Subsequences in compact sets
Suppose that $\{a_k\}_{k=1}^\infty$ is a sequence of real numbers. Then there is a subsequence $\{a_{k_j}\}_{j = 1}^\infty$  that is monotonic
### Bolzano-Weierstrass Theorem
If a bounded sequence is monotonic then it converges to its supreemum / infium.

Start with a sequence in $\mathbb R^n$ and for the first component remove terms until we have a monotonic subsequence and therefore a convergent subsequence for the first term.

We repeat this step on our new sequence for all components of out inital sequence and we get out a subsequence which converge for all components and so converges.

This means that the theorem is true:
A set $\Omega \subseteq \mathbb R^n$ is compact if and only if every sequence in $\Omega$ has a convergent subsequence whose limit is in $\Omega$
## Continuous functions and compactness
For a compact set $K$ and a continuous function $f: K \rightarrow R^n$ we get that the set $f(K)$ is also compact. Thus continuity of functions preserves compactness