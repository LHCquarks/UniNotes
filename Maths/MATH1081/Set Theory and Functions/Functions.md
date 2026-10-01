## Definition
Given two sets $X$ and $Y$ a **function** from $X$ to $Y$ is a subset of $X \times Y$ which contains exactly one ordered pair $(x, y)$ for each $x \in X$.
## Notation
A function from $X$ to $Y$ can be declared as $f: X \rightarrow Y$.

If $(x, y) \in f$ then we say "$f$ **maps** $x$ to $y$" which can also be written as $f: x\mapsto y$  or $f(x) = y$.
We can also refer to $x$ and an **input value** whilst $y$ is an **output value**.
## Domains, codomains ect
The **domain** of a function defined by $f: X \rightarrow Y$ is the set $X$ whilst the set of all potential output values $Y$ is referred to as the **codomain**. 

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
Note that under this definition of pre-image we do not need any or all of $B$ to be in the range of $f$ and only fill our set with elements who are in the range of $f$.
## Injectivity
We define a function as **injective** (one-to-one) iff for all $y \in Y$ there is **at most one** $x\in X$ such that $f(x) = y$.

Note that this does not mean that for all $y$ there exists an $x$ such that $f(x) = y$ but simply there are not two or more $x$. This means the codomain can be larger than the range.
## Surjective
We define a function as **surjective** (onto) iff for all $y \in Y$ there is **at lest one** $x \in X$ such that $f(x) = y$.

This essentially means that the codomain is equal to the range of the function.
## Bijective
We define a function as **bijective** iff the function is both **injective** and **surjective**
## Cardinality of domains and codomains
Take the function $f: X \rightarrow Y$, we know from the definitions of **injectivity, surjectivity and bijectivity** that the following are true:
- If $f$ is **injective** then $|X| \le |Y|$
- If $f$ is **surjective** then $|X| \ge |Y|$
- If $f$ is **bijective** then $|X| = |Y|$
## Function composition
We define the **composition** of two functions $f: X \rightarrow Y, g: Y \rightarrow Z$ as the new function $g \circ f: X \rightarrow Z$ such that:
$$
\begin{align}
(g \circ f)(x) = g(f(x))
\end{align}
$$
This reads as "the composition of $f$ and $g$ equals $g$ of $f$ of $x$".
### Injectivity and surjectivity of composed functions
If $f, g$ are both injective then we get that $g \circ f$ is also injective

If $f, g$ are both surjective then we get that $g \circ f$ is also surjective

Thus if both $f, g$ are bijective then $g \circ f$ is also bijective
## The Identity function
The identity function of and set $X$ is denoted as $\iota_X$ or $\mathbb 1_X$ and is defined as:
$$
\begin{align}
\iota_X : X &\rightarrow X \\
\iota_X(x) = x \ &\ \forall x\in X
\end{align}
$$
### Composition
For any function $f: X \rightarrow Y$ we have that $f \circ \iota_X = f$ and $\iota_Y \circ f = f$. 
## Inverse functions
The inverse of a function $f: X \rightarrow Y$, if it exists, is the function $f^{-1}: Y \rightarrow X$ such that $f\circ f^{-1} = \iota_Y$ and $f^{-1} \circ f = \iota_X$.

This notation looks the same as our pre-image notation however we can distinguish the two based on the element in the parentheses. If the item is a set we are talking about the **pre-image** but if it is an element of $X$ then we are talking about the **inverse**.
### Properties
The inverse of a function $f$ as the following properties:
- It is unique (there is only one $f^{-1}$)
- The inverse of $f^{-1}$ is just $f$ ($\left(f^{-1}\right)^{-1} = f$)
- If both $f, g$ are invertable then $(g\circ f)^{-1} = f^{-1}\circ g^{-1}$
### Existence
The Inverse of a function $f$ exists **if and only if** $f$ is bijective