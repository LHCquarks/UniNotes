## Properties of Sets
$|x| = ||x|| = d_2(x, 0)$ is called the **norm** or **magnitude** of $x$

### Open ball
$\forall a\in \mathbb R^n$ and $\epsilon > 0$ the open ball around $a$ of radius $\epsilon$ is the set
$$
\begin{align}
B(a, \epsilon) = B_\epsilon (a) = \{x \in \mathbb R^n: d(x, a) < \epsilon\}
\end{align}
$$
### Closed ball
A closed ball is simply the **closure** of it's corresponding open ball. It is equivalently defined as:
$$
\begin{align}
\overline{B(a, \epsilon)} = \overline{B_\epsilon (a)} = \{x \in \mathbb R^n: d(x, a) \le \epsilon\}
\end{align}
$$
### Interior points
An interior point $x$ of a subset $\Omega$ of $\mathbb R^n$ is a point such that there exists a $r > 0$ such that $B_r(x) \subseteq \Omega$
### Interior of $\Omega$
The interior of $\Omega$ denoted as $\text{Int}(\Omega)$ is the set of all interior points in $\Omega$
### Openness
A region $\Omega$ is **open** if for every $x \in \Omega$, $x \in \text{Int}(\Omega)$
### Closure
A region $\Omega$ is **closed** if $\Omega^c = \mathbb R^n \backslash \Omega$ is **open**
### Boundary points
$x\in\mathbb R^n$ is a **boundary point** of $\Omega$ if for every $r > 0$, the sets $B_r(x) \cap \Omega \not = \varnothing$ and $B_r(x) \cap \Omega^c \not = \varnothing$
### Boundary of a region
The boundary of a region $\Omega$ is the set of all boundary points of $\Omega$ and is denoted by $\text{Bd}(\Omega)$ or $\partial \Omega$
### Composition of open sets
Suppose that $\Omega$ is a non-empty **open** set. If $x\in \Omega$  then there is an $\epsilon_x > 0$ such that $B(x, \epsilon_x) \subseteq \Omega$. Hence $\Omega = \bigcup_{x\in \Omega} B(x, \epsilon_x)$.
Therefore we can write any non-empty **open** set as the union of balls
### Combination of sets
Suppose that $\Omega_1$ and $\Omega_2$ are two **open** sets.  If their **intersection** is empty then it is also **open**. 
Otherwise for all $x \in \Omega_1 \cap \Omega_2$ we have $\epsilon_1$ and $\epsilon_2$ such that $B(x, \epsilon_1) \subseteq \Omega_1, B(x, \epsilon_2) \subseteq \Omega_2$.

Taking $\epsilon = \min(\epsilon_1, \epsilon_2)$ we have that $B(x, \epsilon) \subseteq \Omega_1 \cap \Omega_2$ and thus the **intersection** of $\Omega_1$ and $\Omega_2$ is also **open**.

Similarly the **Union** of two **open** sets is also **open**

The same thing holds for the **union** of **closed** sets as well as the **intersections** of closed sets.

By induction all of these hold for any finitely many combination their respective sets however it does not hold for infinity many combinations. 
### Cartesian product of two sets
$A \subseteq \mathbb R^n$ and $B \subseteq \mathbb R^m$ are **open** if and only if $A \times B \subseteq \mathbb R^{n + m}$ 
### Alternate definition of closure
A set $\Omega \subseteq \mathbb R^n$ is **closed** if and only if $\partial \Omega \subseteq \Omega$ or in English if it contains all of it's boarder.
## Limit points and Closure
Suppose that $\Omega \subseteq \mathbb R^n$. We say that $x\in \mathbb R^n$ is a **limit point** of $\Omega$ if there exists a sequence $\{x_k\}_{k = 1}^\infty$ that approaches $x$ such that $x_k \in \Omega \backslash \{x\}$.

The closure of $\Omega$ denoted by $\text{cl}(\Omega)$ of $\overline \Omega$ is the union of $\Omega$ and all it's **limit points**

Fairly intuitively we get that a **limit point** of $\Omega$ is either an **interior point** or a **boundary point**.