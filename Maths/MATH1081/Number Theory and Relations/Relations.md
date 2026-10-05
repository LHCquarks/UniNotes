Given two sets $X, Y$ a **relation** from $X$ to $Y$ is a subset $R$ of $X \times Y$.

We say that $x \in X$ is related to $y\in Y$ if $(x, y) \in R$ which can also be written $x \ R \ y$. Further, if $(x, y) \not \in R$ we can write $x \ \not R \ y$. 

Relations can also be represented with many other symbols like $\sim, \prec, \preceq, \simeq$ and so on. Common relations include $=, <, \le, \in, \subseteq, \mid, \equiv$.

## Common properties for some relations
### Reflexivity
For a relation $R \subseteq X \times X$ we call it **reflexive** if for all $x \in X$ we have that $x \ R \ x$.
### Symmetry
For a relation $R \subseteq X \times X$ we call it **symmetric** if for all $x, y \in X$ we have that $x \ R \ y \iff y \ R\ x$.
### Transitivity
For a relation $R \subseteq X \times X$ we call it **transitive** if for all $x, y, z\in X$ we have that $x \ R\ y, y\ R\ z \implies x\ R \ z$. 
### Equivalence relations
A relation $R \subseteq X \times X$ is an **equivalence relation** iff it is **reflexive, symmetric** and **transitive**. If two objects are related by some equivalence relation then we can conclude they are the same in some particular sense.
## Equivalence classes
For a given equivalence relation $\sim\subseteq X \times X$ and an element $a \in X$ we can define the **equivalence class** $[a]$ as the set:
$$
\begin{align}
[a] &= \{x \in X: x \sim a\}
\end{align}
$$
For example if $\sim$ is defined by setting $x \sim y$ if $x \equiv y \pmod{2}$ then $[0] = \{2k: k\in \mathbb Z\}$.
### Properties
- If $x \in X$ then $x \in [x]$
- If $x \sim y$ then $[x] = [y]$
- All the equivalence classes on $X$ **partition** $X$