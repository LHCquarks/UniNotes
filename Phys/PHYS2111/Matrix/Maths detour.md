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
### Proof
Consider $\ket z = \ket v - \frac{\braket{w | v}}{\braket{w|w}} \ket w$.
Now from the 2nd axiom of inner products we know $\braket{z|z} \ge 0$.
We can therefor expand this to:
$$
\begin{align}
0 &\le \braket{z | v - \frac{\braket{w|v}}{\braket{w|w}}w} \\
&= \braket{z|v} - \frac{\braket{w|v}}{\braket{w|w}}\braket{z|w} \\
&= \braket{v - \frac{\braket{w | v}}{\braket{w|w}} w|v} - \frac{\braket{w|v}}{\braket{w|w}}\braket{v - \frac{\braket{w | v}}{\braket{w|w}} w|w} \\
&= \braket{v | v} - \left(\frac{\braket{w | v}}{\braket{w|w}}\right)^*\braket{w|v} - \frac{\braket{w|v}}{\braket{w|w}}\left(\braket{v|w} - \left(\frac{\braket{w | v}}{\braket{w|w}} \right)^* \braket{w|w}\right) \\
&= \braket{v | v} - \frac{|\braket{w | v}|^2}{\braket{w|w}} - \frac{\braket{w|v}}{\braket{w|w}}\left(\braket{v|w} - \left(\frac{\braket{w | v}}{\braket{w|w}} \right)^* \braket{w|w}\right) \\
\end{align}
$$
<% tp.file.cursor(2) %>
## Triangle inequality
$$
\begin{align}
|\ket v + \ket w| \le |\ket v| + |\ket w|
\end{align}
$$
## Operators
Operators are objects that when applied to a vector produce another vector.

We often denote these as capital letters with a hat on them like so: $\hat E$. 
An example expression is:
- $\hat E \ket v = \ket{\hat E v}$
## Hermitian adjoint
We define the **Hermitian Adjoint** of an **operator** $\hat M$ as as being the operator $\hat M ^\dagger$ that satisfies:
$$
\begin{align}
\braket{u|\hat Mv} &= \braket{\hat M^\dagger u | v} \\
\end{align}
$$
We get the following properties for the **hermitian adjoint**:
### $(\hat A^\dagger)^\dagger = \hat A$
For arbitrary vectors $\ket v, \ket w$ we have the two equations:
$$
\begin{align}
\braket{\hat A ^\dagger v | w} &=\braket{v | \hat A w} \tag {1}\\
\braket{w | \hat A^\dagger v} &= \braket{(\hat A^\dagger)^\dagger w | v} \tag{2}
\end{align}
$$
Manipulating the 2nd equation we get:
$$
\begin{align}
\braket{\hat A^\dagger v| w}^* &= \braket{(\hat A^\dagger)^\dagger w | v} \\
\left(\braket{\hat A^\dagger v| w}^*\right)^* &= \braket{(\hat A^\dagger)^\dagger w | v}^* \\
\braket{\hat A^\dagger v| w} &= \braket{v|(\hat A^\dagger)^\dagger w }
\end{align}
$$
Now substituting in equation 1:
$$
\begin{align}
\braket{v | \hat A w} &= \braket{v | (\hat A^\dagger)^\dagger w} \\
\end{align}
$$
Because this equation must hold for all $\ket w$ we get that $\hat A = (\hat A^\dagger)^\dagger$.
### $(\hat A + \hat B)^\dagger = \hat A^\dagger + \hat B^\dagger$
Start by taking:
$$
\begin{align}
\braket{v | (\hat A + \hat B)w} &= \braket{v | (\hat A + \hat B)w} \\
\end{align}
$$
Now the LHS by definition is $\braket{(\hat A + \hat B)^\dagger v | w}$. For the right hand side we can expand like so:
$$
\begin{align}
\text{RHS} &= \braket{v | \hat A w + \hat B w} \\
&= \braket{v | \hat A w } + \braket{v| \hat B w} \\
&= \braket{\hat A^\dagger v | w } + \braket{\hat B^\dagger v| w} \\
&= \braket{\hat A^\dagger v + \hat B^\dagger v| w} \\
&= \braket{(\hat A^\dagger + \hat B^\dagger) v| w} \\
\end{align}
$$
Thus equating the two sides again we find that for all $v$: $\braket {(\hat A + \hat B)^\dagger v| w} = \braket{(\hat A^\dagger + \hat B^\dagger)v | w}$ and thus $(\hat A + \hat B)^\dagger = \hat A^\dagger + \hat B^\dagger$ 
### $(\hat A\hat B)^\dagger = \hat B^\dagger \hat A^\dagger$
Take a similar setup as above:
$$
\begin{align}
\braket{v | (\hat A \hat B)w} &= \braket{v | (\hat A \hat B)w} \\
\end{align}
$$
Now again by definition the LHS is $\braket{(\hat A \hat B)^\dagger v| w}$. On the RHS we apply the operators sequentially like so:
$$
\begin{align}
\text{RHS} &= \braket{v | \hat A (\hat B w)} \\
&= \braket{\hat A^\dagger v | \hat B w} \\
&= \braket{\hat B^\dagger(\hat A^\dagger v) | w} \\
&= \braket{(\hat B^\dagger \hat A^\dagger) v | w} \\
\end{align}
$$
Thus by the same argument as above $(\hat A \hat B)^\dagger = \hat A^\dagger \hat B^\dagger$
### Hermitian adjoint of a scalar
If we have an expression like $\braket{v | cw}$ where c is a scalar then we can take $c$ out like so $c\braket{v | w}$ and put it back into the left hand side like so $\braket{c^*v| w}$ and thus the **Hermitian adjoint** of a scalar is just the conjugate.
$$
\begin{align}
c^\dagger = c^*
\end{align}
$$
### Hermitian adjoint of bras and kets
Lets consider the inner product between two vectors $\braket{v | w}$. Because the inner product just returns a scalar we can use our previous law to find it's **hermitian adjoint**:
$$
\begin{align}
\braket{v | w}^\dagger &= \braket{v | w}^* \\
&= \braket{w | v}
\end{align}
$$
Now lets break up the inner product and test what we get:
$$
\begin{align}
\braket{v | w}^\dagger &= (\bra v \ket w)^\dagger \\
&= \ket w^\dagger \bra v^\dagger
\end{align}
$$
This tells us that the **Hermitian adjoint** of a bra is a ket and vice versa
