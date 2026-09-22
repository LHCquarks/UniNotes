## Definition
Given two sets $X$ and $Y$ a **function** from $X$ to $Y$ is a subset of $X \times Y$ which contains exactly one ordered pair $(x, y)$ for each $x \in X$.
## Notation
A function from $X$ to $Y$ can be declared as $f: X \rightarrow Y$.

If $(x, y) \in f$ then we say "$f$ **maps** $x$ to $y$" which can also be writen as $f: x\mapsto y$  or $f(x) = y$.
We can also refer to $x$ and an **input value** whilst $y$ is an **output value**.
## Domains, codomains ect
The **domain** of a function defined by $f: X \rightarrow Y$ is the set $X$ whilst the set of all potential output values $Y$ is refered to as the **codomain**. 

The **range** of a function is the set of all output values actually obtained by our function. This is also called the **image** of our function and is given by:
$$
\begin{align}
\text{im}(f) = \text{range}(f) = f(X) = \{f(x): x \in X\} \subseteq Y
\end{align}
$$
## Image and pre-image
The **image** of a set $B \subseteq X$ under a function $f: X \rightarrow Y$  is a set $f(A)$ given by:
$$
\begin{align}
f(A) = \{f(x): x \in A\} \subseteq Y
\end{align}
$$
The **pre-image** of a set $B \subseteq Y$ under $f: X \rightarrow Y$ is given by:
$$
\begin{align}
f^{-1}(B) &= \{x \in X : f(x) \in B\} \subseteq X
\end{align}
$$
## Injectivity
We define a function as **injective** (one-to-one) iff for all $y \in Y$ there is **at most one** $x\in X$ such that $f(x) = y$.

Note that this does not mean that for all $y$ there exists an $x$ such that $f(x) = y$ but simply there are not two or more $x$. This means the codomain can be larger than the range.
## Surjective
We define a function as **surjective** (onto) iff for all $y \in Y$ there is **at lest one** $x \in X$ such that $f(x) = y$.

This essentially means that the codomain is equal to the range of the function.
## Bijective
We define a function as **bijective** iff the function is both **injective** and **surjective**