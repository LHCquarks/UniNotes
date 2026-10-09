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
## Equivalence relations
A relation $R \subseteq X \times X$ is an **equivalence relation** iff it is **reflexive, symmetric** and **transitive**. If two objects are related by some equivalence relation then we can conclude they are the same in some particular sense.
### Equivalence classes
For a given equivalence relation $\sim\subseteq X \times X$ and an element $a \in X$ we can define the **equivalence class** $[a]$ as the set:
$$
\begin{align}
[a] &= \{x \in X: x \sim a\}
\end{align}
$$
For example if $\sim$ is defined by setting $x \sim y$ if $x \equiv y \pmod{2}$ then $[0] = \{2k: k\in \mathbb Z\}$.
#### Properties
- If $x \in X$ then $x \in [x]$
- If $x \sim y$ then $[x] = [y]$
- All the equivalence classes on $X$ **partition** $X$
## Partial orders
### Anti-symmetry
A relation $\preceq$ is considered anti-symmetric if for all $x, y \in X$ whenever $x \preceq y$ and $y \preceq x$  we have that $x = y$.
### Partial Order
A relation $\preceq$ is a **partial order** iff it is **reflexive, antisymetric** and **transitive**. 

An example of a partial order is $\le$ or $\subseteq$.
### Comparable objects
Two objects $x, y$ are related by the partial order $\preceq$ if **either** $x \preceq y$ or $y \preceq x$.

If two objects are related by a partial order relation we say they are **comparable**.
Further, if $x \preceq y$ we say that "$x$ **precedes** $y$" and if $y \preceq x$ we say that "$x$ **succeeds** $y$".
### Partially and totally ordered sets
If $\preceq$ is a partial order on a set $X$ we call $X$ a **partially ordered set** or **poset** which we can write as $(X, \preceq)$.

Further, if a poset has the property that all it's elements are comparable to each other then our set is a **totally ordered set**. 

An example of one such set is $(\mathbb R, \le)$. 
### Minimal and Maximal elements
A **minimal** element of a poset is an element $x \in X$ such that there is no $y \in X$ such that $y\preceq x$ .
A **maximal** element of a poset is an element $x \in X$ such that there is no $y \in X$ such that $x\preceq y$ .

Note that multiple elements of $X$ can be maximal and minimal but they can not relate to each other.
### Greatest and least elements
The **greatest** element of a poset $(X, \preceq)$ (if it exists) is the element $x \in X$ such that for all $y \in X$ we have that $y \preceq x$.

The **least** element of a poset $(X, \preceq)$ (if it exists) is the element $x\in X$ such that for all $y \in X$ we have that $x \preceq y$.

We have that:
- The least element is unique
- The greatest element is unique
- If $X$ is finite then $(X, \preceq)$ has a **least** element iff there is exactly one **minimal** element
- If $X$ is finite then $(X, \preceq)$ has a **greatest** element iff there is exactly one **maximal** element
### Lower and upper bounds
A **lower bound** of two elements $x, y \in X$ is an element $z\in X$ such that $z \preceq x$ and $z \preceq y$.

A **upper bound** of two elements $x, y \in X$ is an element $z\in X$ such that $x \preceq z$ and $y \preceq z$.

We can then define the functions for the greatest lower bound and least upper bounds as $\text{glb}(x, y)$ and $\text{lub}(x, y)$ respectively.

### Relations other areas
Take a set $S$ then we can construct the poset $(\mathcal P(S), \subseteq)$. Within this poset $\text{glb}(A, B) = A \cap B$ whilst $\text{lub}(A, B) = A \cup B$.

Take the poset $(\mathbb Z^+, \mid)$ then we have $\text{glb}(a, b) = \gcd(a, b)$ and $\text{lub}(a, b) = \text{lcm}(a, b)$.
