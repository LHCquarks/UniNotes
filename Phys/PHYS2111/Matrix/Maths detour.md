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

In Bra Ket notation we write the inner product between vectors $\ket v, \ket w$ as $\braket {v|w}$.
An inner product must follow these 3 properties:
1. $\braket{v|w} = \braket{w|v}^*$
2. $\braket{v|v} \ge 0$
	- We also need $\braket{v|v} = 0$ iff $\ket v = \ket 0$
3. $\braket{u|av + bw} = a\braket{u|v} + b\braket{u|w}$
### Length of a vector
From this definition of the inner product of our vectors we are able to define the **length** of our vector as:
$$
\begin{align}
|\ket v| &= \sqrt{\braket{v | v}}
\end{align}
$$
We also call all vectors where $|\ket v| = 1$ a **normal vector**
### Linearity in the bra
Notice how in axiom 3 we only assumed that the inner product was linear on the ket. The corresponding law for bras can be proven from the axioms as done bellow:
$$
\begin{align}
A &= \braket{au + bv | w} \\
&= \braket {w | au + bv}^* \tag {1}\\ 
&= a^*\braket{w|u}^* + b^*\braket{w|v}^* \tag{3}\\
&=  a^*\braket{u|w} + b^*\braket{v|w} \\

\end{align}
$$
We call this property of the left slot anti linearity as the coefficients are conjugated
### Orthogonality
We define two vectors $\ket v, \ket w$ as **orthogonal** if  $\braket{v|w} = \braket {w|v} = 0$.

Whilst thinking of this as being "90 degrees" from one another does not always make scene many of the properties are the same.
### Normalization
If you have a vector $\ket v \not = \ket 0$ you can always find an $a\in \mathbb F$ such that $\ket u = a\ket v$ and $\braket{u|u} = 1$.

We have that this special $a$ is any scalar satisfying
$$
\begin{align}
|a| = \frac{1}{\sqrt{\braket{v | v}}}
\end{align}
$$
We prove this bellow:
$$
\begin{align}
\ket u &= a\ket v \\
\braket{u | u} &= \braket{u|av} \\
&= a\braket{u|v} \tag{3} \\
&= a\braket{av|v} \\
&= aa^*\braket{v|v} \\
&= |a|^2\braket{v|v} \\
&= \frac{\braket{v|v}}{\braket{v|v}} \\
&= 1
\end{align}
$$
### Inner product examples
For the real valued 3d vectors our inner product is just the dot product

For real valued functions defined on $[0, L]$ that have $f(0) = f(L) = 0$ the inner product is:
$$
\begin{align}
\int_0^Lf(x)g(x)dx
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
## Operators
Operators are objects that when applied to a vector produce another vector.

We often denote these as capital letters with a hat on them like so: $\hat E$. They 
## Conjugate transpose / adjoint operation / Hermitian conjugate
We define the **Hermitian Conjugate** as:
$$
\begin{align}
(a\ket v)^\dagger &=  ((a\ket v)^T)^*
\end{align}
$$
