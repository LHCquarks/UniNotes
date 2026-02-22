## Vector spaces
A **Vector space** $V$ is a set that contains elements called **vectors**, is equipped with operations $+$ and $\times$ that operate on two vectors and a vector plus a scalar field $\mathbb F$ respectively.

Further, these vectors and operations must satisfy the following 10 axioms:
For all vectors $\ket v, \ket w, \ket u \in V$ and scalars $a, b \in \mathbb F$
1. $\ket v + \ket w \in V$ 
2. $a \times \ket v \in V$
3. $\ket v + \ket w = \ket w + \ket v$
4. $\ket v + (\ket w + \ket u) = (\ket v + \ket w) + \ket u$
5. There exists $\ket 0$ such that $\ket v + \ket 0 = \ket v$
6. There exists $\ket {-v}$ such that $\ket v + \ket {-v} = \ket 0$
7. $a\times (b \times \ket v) = (ab)\times \ket v$
8. $1\times \ket v = \ket v$
9. $a \times ( \ket v + \ket w) = a \times \ket v + a \times \ket w$
10. $(a + b) \times \ket v = a \times \ket v + b \times \ket v$

## Inner product space
An **inner product space** is a **vector space** equipped with an operation called an **inner product**  that operates on two vectors and returns a scalar. 

In Bra Ket notation we write the inner product between vectors $\ket v, \ket w$ as $\braket {v|w}$ 


## Conjugate transpose / adjoint operation
We define the **conjugate transpose** of a vector and scalar as:
$$
\begin{align}
\ket {av} &= a \ket v \\
\ket {av}^\dagger &= (a \ket v) ^ \dagger \\
\bra{av}
\end{align}
$$
## Schwarz Inequality
For all vectors:
$$
\begin{align}
|\braket{v | w}|^2 \le \braket{v|v}\braket{w|w}
\end{align}
$$
## Triangle inequality
$$
\begin{align}
|\ket v + \ket w| \le |\ket v| + |\ket w|
\end{align}
$$
