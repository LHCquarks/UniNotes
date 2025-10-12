## Description
FLTs transform lines and circles into lines and circles.
## Definition
For some complex number $z$ that varies we map it to a new value $f(z)$ such that
$$
\begin{align}
f(z) = \frac{az+b}{cz+d}
\end{align}
$$
for some complex $a, b, c, d \in \mathbb{C}$ where $ad - bc \neq 0$.

## How to tell if $f(z)$ varies on a line or circle
If the points where $z$ varies include the point $z = -\frac{d}{c}$ than $f(z)\rightarrow \infty$ hence $f(z)$ varies on a line.

Otherwise, If there is no point where $z = -\frac{d}{c}$ then $f(z)$ is a circle.
## Finding the equation of the line / circle
This is easy as all you need is 2 points for to find the entire equation of the line or 3 for the equation of a circle
## Connection to linear algebra
A fractional linear transformation can also be constructed with matrices and vector. Consider the complex number $z = x+iy$ and the vector $\begin{pmatrix}x\\y\end{pmatrix}$.

With the above setup
$$
\begin{align}
\begin{pmatrix}
a & b \\ c & d
\end{pmatrix}
\end{align}
$$
and $$
\begin{align}
f(z) = \frac{az+b}{cz+d}
\end{align}
$$
behave the same to their respective inputs. This relation leads us to denote fractional linear transformations that follow the matrix
$$
\begin{align}
M =
\begin{pmatrix}
a & b \\ c& d
\end{pmatrix}
\end{align}
$$
as $$T_M(z) = \frac{az+b}{cz+d}$$

### Restrictions on $M$
#### $c, d \not = 0$
Obviously, we can not have that $c, d = 0$ as we would then be dividing by $0$.
#### $\text{Det}(M) \not = 0$
Further, we can deduce that if $Det(M) = 0$ then $\begin{pmatrix} a \\ b \end{pmatrix} = \lambda \begin{pmatrix} c \\ d \end{pmatrix}$ and so $\frac{\lambda(cz+d)}{cz+d} = \lambda$ and therefor this becomes a constant function which is not very interesting and thus we will not include it.

#### $\text{Det}(M) = 1$

##### Scalar of a $M$
###### Lemma
If $\lambda \not = 0$:
$$T_{\lambda M} = T_M$$
###### Proof
Take $T_{\lambda M}$, then
$$
\begin{align}
T_{\lambda M}(z) &= \frac{\lambda az + \lambda b}{\lambda c z + \lambda d} \\
&= \frac{az + b}{c z +d} \\
&= T_{M}(z)
\end{align}
$$
###### Effect
For this reason we can only consider mappings derived from matrices where $det(M) = 1$ as we can all linear maps have an equivalent map derived from this.
## Domain and range
### Domain
If $c = 0$ then we get that $\text{Domain}(T_M) = \mathbb{C}$
If $c\not=0$ then we get that $\text{Domain}(T_M) = \mathbb{C} \backslash (-d/c)$ 

### Range
Suppose $w \in \text{Range}(T_M)$
$$
\begin{align}
w &= \frac{az+b}{cz+d} \\
w(cz + d) &= az + b \\
wcz + wd &= az + b \\
wcz - az &= b - wd \\
z(wc - a) &= b-wd \\
wc - a \not = 0 \implies & \\
z &= \frac{b-wd}{wc-a} \\
\end{align}
$$
This implies that:

If $c \not = 0$ then we get $\text{Range}(T_M) = \mathbb{C}$
If $c = 0$ then we get $\text{Range}(T_M) = \mathbb{C} \backslash \frac{a}{c}$
### Simplifying the domain and range
We define a number $\infty$ by
$T_M(-d/c) = \infty$ and $T_M(\infty) = a/c$

We can make this definition rigorous via the Riemann sphere

## Composition
For two matrices $M, N$ then 
$$T_M T_N = T_{MN}$$
This implies that
$$
\begin{align}
T_M T_{M^{-1}} &= T_I \\
&= \frac{z}{1} \\
&= z
\end{align}
$$

## Use of linear algebra
### Theorem from linalg
Every $M \in M_{2, 2}(\mathbb{C})$ with $\det(M) = 1$ can be written as a product of at most 3 matrices of the form:
$$
\begin{align}
\begin{pmatrix}
* & * \\
0 & *
\end{pmatrix}
\end{align}
$$
or 
$$
\begin{align}
\begin{pmatrix}
0 & 1 \\ -1 & 0
\end{pmatrix}
\end{align}
$$
### Factorizing FTLs
Because you can factorize matrices any matrix by above we can factorise any FTL into at most 3 FLTs of the above matrices
#### What each of these matrices do
##### $\begin{align}\begin{pmatrix}* & * \\ 0 & *\end{pmatrix}\end{align}$

This has the form 
$$
\begin{align}
T_M(z) &= \frac{az + b}{0z + d} \\
&= \frac{a}{d}z + \frac{b}{d}
\end{align}
$$
and so is a affine transformation
##### $\begin{pmatrix}0 & 1 \\ -1 & 0\end{pmatrix}$

This has the form
$$
\begin{align}
T_M(z) &= \frac{0z+1}{-1z+0} \\
&= \frac{1}{-z} \\
&= -z^{-1}
\end{align}
$$
