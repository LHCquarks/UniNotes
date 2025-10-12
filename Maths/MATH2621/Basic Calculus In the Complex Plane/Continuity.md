## Definitions
Let $f: S \rightarrow \mathbb{C}$ be a complex function and let $z_0 \in S$. We say that:
- $f$ is continuous at $z_0$ if
$$
\begin{align}
\lim_{z\rightarrow z_0} f(z) = f(z_0)
\end{align}
$$
- $f$ is continuous in $S$ if it is continuous at all points of $S$
- $f$ is continuous if it is continuous in its domain

## Combinations
Let $f, g: S \rightarrow \mathbb{C}$ be continuous complex functions and $c \in \mathbb{C}$. The functions:
$$
\begin{align}
&cf, \\ &f+g, \\ &|f|, \\ &\bar f, \\ &\text{Re}(f), \\ &\text{Im}(f), \\ &fg
\end{align}
$$
are all continuous in $S$, as is $f/g$ provided $g(z) \not = 0$ for any $z \in S$.

Further, for continuous complex functions $f, g$ who's domains are $S, T \in \mathbb{C}$ respectively we get that $f \circ g$ is continuous where it is defined.

## Extreme value theorem
Suppose that a continuous complex function $f$ is defined on a compact set $S$.
Then there exists $z_0 \in S$ such that
$$
|f(z_0)| = \max\{ |f(z)|: z \in S \}
$$
and a $z_1 \in S$ such that
$$
|f(z_1)| = \min\{ |f(z)|: z \in S \}
$$