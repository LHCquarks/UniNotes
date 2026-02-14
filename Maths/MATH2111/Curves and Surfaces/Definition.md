## Paths and Curves
### Basic Objects
Assuming that $I$ is an interval:
- A **path** in $\mathbb R ^n$ is a **continuous** function $c: I \rightarrow \mathbb R ^n$
- The **image** of $c$ i.e. $c(I) = \{c(t): t \in I\}$ is called a **curve**
- The function $c$ is called a **parameterisation** of the curve
- If we were to write $c(t) = (c_1(t), c_2(t), ..., c_n(t))$, the functions $c_i: I \rightarrow \mathbb R$ are called the **components** of $c$

### Special points and properties
Supposing that $c: I \rightarrow \mathbb R ^n$ is a **path**:
- A **multiple point** is a point $x \in \mathbb R^n$ such that there exist two unique $t_1, t_2 \in I$ such that $c(t_1) = c(t_2)$
- If $I = [a, b]$ then $c(a)$ and $c(b)$ are **endpoints**
- A **path** is **closed** iff $c(a) = c(b)$
![[Inf.png]]
## Surfaces
MATH2111 Does not rigorously define what a surface is and instead just deals with intuitive surfaces.
### Paramaterisation
A surface $S$ is **parametrically** defined if it can be expressed is the image of a **continuous** function $\rho: D \rightarrow \mathbb R^n$ where $D \subseteq \mathbb R^2$. That is
$$
\begin{align}
S = \rho(D) = \{\rho(s, t): (s, t) \in D\}
\end{align}
$$
Where $D$ is a **domain** or **region** defined in MATH2621

