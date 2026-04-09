Quantum mechanics is basically built off of linear algebra so here we discuss some particularly useful concepts for quantum mechanics:
## Vector spaces
A **Vector space** $V$ is a set that contains elements called **vectors**, is equipped with operations $+$ and $\times$ that operate on two vectors and a vector plus a scalar field $\mathbb F$ respectively.

Further, these vectors and operations must satisfy the following 10 axioms:
For all vectors $\vec{v}, \vec w, \vec u \in V$ and scalars $a, b \in \mathbb F$
1. $\vec v + \vec w \in V$ 
2. $a \times \vec v \in V$
3. $\vec v + \vec w = \vec w + \vec v$
4. $\vec v + (\vec w + \vec u) = (\vec v + \vec w) + \vec u$
5. There exists $\vec 0$ such that $\vec v + \vec 0 = \vec v$
6. There exists $\overrightarrow {(-v)}$ such that $\vec v + \overrightarrow {(-v)} = \vec 0$
7. $a\times (b \times \vec v) = (ab)\times \vec v$
8. $1\times \vec v = \vec v$
9. $a \times ( \vec v + \vec w) = a \times \vec v + a \times \vec w$
10. $(a + b) \times \vec v = a \times \vec v + b \times \vec v$
Note that it can be proven that this $\overrightarrow{(-v)}$ is equivalent to $-1 \times \vec v$
## The dual space
For any given vector space $V$ there exists another vector space $D$ called the **dual space of $V$** consisting of all linear functions on $V$ that return a scalar in the field of $V$.

For the set of column vectors this is the set of all of the row vectors.
## Bra-ket notation
In quantum mechanics we make a lot of use of vectors and their duals and so we have some special notation to make our life easier when dealing with them.
We represent vectors with kets like this: $\ket v$ and duals with bras like this: $\bra w$.
Together they form a bra-ket: $\bra w \ket v$. Get it ... bracket.

Although initially this might seem a little silly, (why another standard?) the true power of **bra-ket** notation is realized with **inner products**
## Inner product space
An **inner product space** is a **vector space** equipped with an operation called an **inner product**  that operates on two vectors and returns a scalar. 

In Bra-ket notation we write the inner product between vectors $\ket v, \ket w$ as $\braket {v|w}$.
An inner product must follow these 3 properties:
1. $\braket{v|w} = \braket{w|v}^*$
2. $\braket{v|v} \ge 0$
	- We also need $\braket{v|v} = 0$ iff $\ket v = \ket 0$
3. $\braket{u|av + bw} = a\braket{u|v} + b\braket{u|w}$
Surprisingly, this inner product $\braket{v | w}$ is equivalent to just multiplying $\bra v \ket w$ hence the true power of bra-ket notation is seen, we can easily break apart our inner products into bras and kets and vice versa.
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
For the real valued vectors our inner product is just the dot product

For real valued functions defined on $[0, L]$ that have $f(0) = f(L) = 0$ the inner product is:
$$
\begin{align}
\int_0^Lf(x)g(x)dx
\end{align}
$$
### Hilbert space
A **Hilbert space** is a real or complex inner product space that is complete (Review Maths2111 point set topology for the definition of completeness). That had finite or infinite dimensions
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
&= \braket{v | v} - \frac{|\braket{w | v}|^2}{\braket{w|w}} - \frac{\braket{w|v}}{\braket{w|w}}\braket{w|v}^* - \frac{\braket{w|v}}{\braket{w|w}}{\braket{w | v}^*} \\
&= \braket{v | v} - \frac{|\braket{w | v}|^2}{\braket{w|w}} - \frac{|\braket{w|v}|^2}{\braket{w|w}} - \frac{|\braket{w|v}|^2}{\braket{w|w}}\\
3\frac{|\braket{w | v}|^2}{\braket{w|w}} &\le \braket{v | v}\\
3|\braket{w | v}|^2 &\le \braket{v | v}\braket{w|w}\\
|\braket{w | v}|^2 &\le \braket{v | v}\braket{w|w}\\
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

We often denote these as capital letters with a hat on them like so: $\hat E$. 
An example expression is:
- $\hat E \ket v = \ket{\hat E v}$
### Eigenvectors and eigenvalues
For an operator $\hat E$ there exists vectors $\ket {e_i}$ and corresponding values $e_i$ such that:
$$
\begin{align}
\hat E \ket {e_i} = e_i \ket {e_i}
\end{align}
$$
These vectors and values are called **eigenvectors** and **eigenvalues** of $\hat E$ respectively.
These objects are central to quantum mechanics and as such we will be seeing a lot of them.

If $\hat E$ is a matrix we can find it's **eigenvalues** through solving the polynomial produced from
$$
\begin{align}
\text{det}(\hat E - e_i I) &= 0 \\
\end{align}
$$
We can then also find the corresponding **eigenvectors** through solving the simultaneous equations produced from
$$
\begin{align}
(\hat E - e_i I) \ket {e_i} &= 0
\end{align}
$$

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
This tells us that the **Hermitian adjoint** of a bra is a ket and vice versa. This Is huge as we now know how to transform a ket into it's corresponding bra, just take the hermitian adjoint!
### Hermitian adjoint of a matrix
Take a matrix $\hat \Omega$, which has matrix elements indexed with $\hat \Omega_{i , j}$ then the hermitian adjoint is found bellow:
$$
\begin{align}
(\hat \Omega ^\dagger)_{i, j} &= \braket{i | \hat \Omega ^\dagger | j} \\
&= \braket{\hat \Omega i | j} \\
&= \braket{j | \hat \Omega i }^* \\
&= \braket{j | \hat \Omega | i }^* \\
&= (\hat \Omega_{j, i})^* \\
\end{align}
$$
Thus the hermitian conjugate of a matrix is the conjugate transpose of the matrix or in cleaner notation $\hat \Omega^\dagger = (\hat \Omega^T)^*$
## Orthonormal basis
An **orthonormal basis** of vector space $V$ with dimension $n \in [0, \infty]$ is a set of vectors $\mathcal B\{\ket i: 1 \le i \le n\}$ with the following properties
- All vectors are **orthogonal**
	- For $\ket i, \ket j \in \mathcal B: \ket i \not = \ket j$ we have $\braket{i|j} = 0$
- All vectors are **normal**
	- For $\ket i \in \mathcal B$ we have $\braket{i|i} = 1$
- $\mathcal B$ is a basis for the vector space $V$
	- $\mathcal B$ is linearly independent
	- All vectors of $V$ are linear combinations of vectors in $\mathcal B$

If we have an **orthonormal basis** we can uniquely expand any vector in terms of the basis like so:
$$
\begin{align}
\ket v = v_0 \ket 0 + v_1 \ket 1 + ... + v_n \ket n
\end{align}
$$
### Kronecker delta
The kronecker delta is an object defined as such:
$$
\begin{align}
\delta_{i, j} = \begin{cases} 1 & i = j\\ 0 & i \not= j \end{cases}
\end{align}
$$
This object can be a very useful notation especially when working with inner products of orthonormal basis as:
$$
\begin{align}
\braket{i | j} = \delta_{i, j}
\end{align}
$$
Further when we have a double sum involving a kronecker delta it can be collapsed easily:
$$
\begin{align}
\sum_{i} \sum_j a_{i, j} \delta_{i, j} &= \sum_i a_{i, i} \delta_{i, i} \\
&= \sum_i a_{i, i} (1) \\
&= \sum_i a_{i, i} \\
\end{align}
$$
### inner product using orthonormal basis
Take the inner product of two vectors $\ket v, \ket w$ and their inner product
$$
\begin{align}
\braket{v | w} &= \braket{v | \sum_j w_i \ket i} \\
&= \sum_i w_i\braket{v | i} \\
&= \sum_i w_i \braket{\left(\sum_j v_j \bra j \right)| i} \\
&= \sum_i w_i \sum_j v_j^* \braket{ j | i} \\
&= \sum_i \sum_j w_i v_j^* \braket{ j | i} \\
&= \sum_i \sum_j w_i v_j^* \delta_{i, j} \\
&= \sum_i w_i v_i^* \\
\end{align}
$$
## Operator types
There are 3 special types of operators:
- **Hermitian** such that $\hat \Omega = \hat \Omega ^ \dagger$
- **Anti-Hermitian** such that $\hat \Omega ^ \dagger = - \hat \Omega$
- **Unitary** such that $\hat \Omega ^ \dagger \hat \Omega = \hat I$
Key facts about these operators are bellow:
1. We can decompose any operator $\hat \Lambda$ into hermitian and anti-hermitian parts like so
$$
\begin{align}
\hat \Lambda &= \frac{\hat \Lambda + \hat \Lambda ^\dagger}{2} + \frac{\hat \Lambda - \hat \Lambda^\dagger}{2}
\end{align}
$$
Where the left hand side of the sum is **Hermitian** and the right hand side is **Anti-Hermitian**.

2. Further, **Unitary** operators preserve inner products so:
$$
\begin{align}
\braket{\hat U v_1 | \hat U v_2} &= \braket {v_1 | \hat U^\dagger \hat U v_2} \\
&= \braket{v_1 | I v_2} \\
&= \braket {v_1 | v_2}
\end{align}
$$
3. Eigenvalues of **Hermitian** operators are real, and eigenvectors corresponding to distinct eigenvalues are orthogonal
## Fourier Transforms
In this course we define the Fourier transform of a function $f$ as:
$$
\begin{align}
\mathcal F(\omega) &= \frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty f(x) e^{-i\omega x}dx
\end{align}
$$
If we have the Fourier transform of a function then we can derive the original function by:
$$
\begin{align}
f(x) &= \frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty \mathcal F(\omega) e^{i\omega x} d\omega
\end{align}
$$
This is essentially representing our function $f(x)$ in the $e^{i\omega x}$ basis
### Common Fourier Transforms
$$
\begin{align}
f(x) = e^{-\frac{1}{2}x^2} &\rightarrow \mathcal F(\omega) = e^{-\frac{1}{2}\omega^2} \\
f(x) = \begin{cases}1 & |x| \le 1/2 \\ 0 & |x| > 1/2 \end{cases} & \rightarrow \mathcal F(\omega) = \frac{1}{\sqrt{2\pi}} \frac{\sin(\frac{\omega}{2})}{\frac{\omega}{2}} \\
f(x) = \cos(x) &\rightarrow \mathcal F(\omega) = \sqrt{2\pi} \frac{1}{2}[\delta(\omega - 1) + \delta(\omega + 1)]
\end{align}
$$
### Special properties
We can always decompose a function into odd and even parts so that:
$$
\begin{align}
f(x) &= \text{even}(x) + \text{odd}(x)
\end{align}
$$
and thus ...

The Fourier transform is linear:
$$
\begin{align}
\alpha f(x) + \beta g(x) \rightarrow \alpha\mathcal F(\omega) + \beta \mathcal G(\omega)
\end{align}
$$
Scaling turns into inverse scaling:
$$
\begin{align}
f(ax) \rightarrow \frac{1}{|a|} \mathcal F\left(\frac{\omega}{a}\right)
\end{align}
$$
Derivatives turn into multiplication by $i\omega$:
$$
\begin{align}
\frac{d}{dx}f(x) \rightarrow i\omega\mathcal F(\omega)
\end{align}
$$
Normalization is preserved:
$$
\begin{align}
\int_{-\infty}^\infty |f(x)|^2dx \implies \int_{-\infty}^\infty |\mathcal F(\omega)|^2 d\omega
\end{align}
$$
