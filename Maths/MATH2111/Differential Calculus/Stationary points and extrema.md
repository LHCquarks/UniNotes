## Critical points
We define **critical** points of a function $f: \Omega \rightarrow \mathbb R$ as points that satisfy:
- $\vec a$ is a stationary point so $\nabla f(\vec a) = \vec 0$
- $\vec a$ is on the boundary of $\Omega$ so that $\vec a \in \partial \Omega$
- $\vec a \in \text{Int}(\Omega)$ is a non-differentiable point on $\Omega$

## Classifying stationary points
Stationary points are points defined as $\nabla f(\vec a) = \vec 0$.

We can expand our function $f$ as a taylor polynomial like so:
$$
\begin{align}
f(\vec x)  = f(\vec a) + \nabla f(\vec a) \cdot (\vec x - \vec a) + 
\frac{1}{2} \left((\vec x - \vec a) H_f(\vec a) (\vec x - \vec a)^T\right) +
R_{2, \vec a}(\vec x)
\end{align}
$$
Now noticing the second term is zero and the final term goes to zero as $\vec x \rightarrow \vec a$ we get that
$$
\begin{align}
f(\vec x) = f(\vec a) + 
\frac{1}{2} \left((\vec x - \vec a) H_f(\vec a) (\vec x - \vec a)^T\right)
\end{align}
$$
Assuming our function is continuously second differentiable then $H_f(\vec a)$ is real and symmetric and thus has real eigenvalues and we can construct an orthonormal eigenbasis. In the case that $\vec x - \vec a$ is an eigenvector of $H_f(\vec a)$ and is small we get that
$$
\begin{align}
f(\vec x) &\approx f(\vec a) + \frac{1}{2} ((\vec x - \vec a) \lambda (\vec x - \vec a)^T) \\
&= f(\vec a) + \frac{1}{2} \lambda((\vec x - \vec a) \cdot (\vec x - \vec a)) \\
&= f(\vec a) + \frac{1}{2} \lambda |\vec x - \vec a|^2 \\
\end{align}
$$
Now for each eigenvector if it's eigenvalue is positive then our function is increasing and if its negative then the function is decreasing in the direction of the eigenvector.

Thus if all **eigenvalues** of our $H_f(\vec a)$ is **positive** then our stationary point is a **local minimum** and if our **eigenvalues** are **negative** then our stationary point is a **local maximum**. In any other scenario our point is a **saddle point**

If **zero** is an eigenvalue then we **can not conclude anything** as our third order terms become relevant then
### Sylvester's criterion
From on high we are given the fact that for an $n \times n$ symmetric matrix $M$ we can construct $k \times k$ matrices $M_k$ made out of the top corner of our original matrix and the following facts hold:
- The eigenvalues of $M$ are $\lambda > 0$ if and only if $\det(M_k) > 0$ for all $k$
- The eigenvalues of $M$ are $\lambda \ge 0$ implies $\det(M_k) \ge 0$ for all $k$
- The eigenvalues of $M$ are $\lambda < 0$ if and only if $(-1)^k\det(M_k) > 0$ for all $k$
- The eigenvalues of $M$ are $\lambda \le 0$ implies $(-1)^k\det(M_k) \ge 0$ for all $k$
#### Example
Because this was fairly opaque for me the first time reading through here is an example:
$$
\begin{align}
M &= \pmatrix{\ \ 2 & -1 & \ \ 0 \\ -1 & \ \ 2 & -1 \\ \ \ 0 & -1 & \ \ 2}
\end{align}
$$
Then:
$$
\begin{align}
M_1 &= \pmatrix{2} \implies \det(M_1) = 2 > 0 \\
M_2 &= \pmatrix{\ \ 2 & -1 \\ -1 & \ \ 2} \implies \det(M_2) = 4 - 1 > 0 \\
M_3 &= \pmatrix{\ \ 2 & -1 & \ \ 0 \\ -1 & \ \ 2 & -1 \\ \ \ 0 & -1 & \ \ 2} \implies \det(M_3) = 2(4) - (-1)(-(1)2 - 0) + 0  = 8 - 2 > 0 \\
\end{align}
$$
Thus $M$ has only positive eigenvalues

### $2 \times 2$ case
For 2x2 matrices we know that $\text{Tr}(M) = \lambda_1 + \lambda_2$ and $\det(M) = \lambda_1 \lambda_2$ so:
- $M$ has positive eigenvalues if and only if $\text{Tr}(M) > 0$ and $\det(M) > 0$
- $M$ has negative eigenvalues if and only if $\text{Tr}(M) < 0$ and $\det(M) > 0$
- $M$ has opposite eigenvalues if and only if $\det(M) < 0$
## Global maxima and minima
For points on a **compact** set $\Omega$ we can guarantee that there exists a **global maximum** and **global minimum** for a function $f: \Omega \rightarrow \mathbb R$.

We can also guarantee all local and global maxima and minima occur at **critical** points of $f$.

Usually when finding these points we want to argue that our maxima can not be on the boundary of the function and there are no non-differentiable points of the interior of $\Omega$ so that all potential points occur when $\nabla f(\vec a) = \vec 0$.
## Lagrange Multipliers
Being able to find global maxima and minima is great but what if we are limited to a constraint?

For this we consult the great Lagrange who bestows us with the formula:
$$
\begin{align}
\nabla f(\vec a) = \lambda \nabla g(\vec a)
\end{align}
$$
where:
- $f$ is our extremizing function
- $\vec a$ is an extreme point of $f$
- $\lambda$ is some arbitrary constant
- $\nabla g$ is a normal vector to our constraint surface

This formula works because stationary points of our surface coincide with the level curves of $f$. Noting that $\nabla f$ is normal to the level curve we know that at a stationary point $\nabla g$ will be in the same direction as $\nabla f$. 
### Example
Say we want to find the min and max values of $f(x, y) = 2x + 2y$ on the constraint of $x^2 + y^2 = 4$. Start by observing that $x^2 + y^2 = 4$ is a compact subset of $\mathbb R^2$ so there is guaranteed to be a global max and min.

We now define $g(x, y) = x^2 + y^2 = 4$ thus the normal to our surface is $\nabla g(x, y)$

Using Lagrange's equation we get:
$$
\begin{align}
\nabla f (\vec a) &= \lambda \nabla g(\vec a) \\
\pmatrix{2 \\ 2} &= \lambda \pmatrix{2x \\ 2y} \\
\end{align}
$$
so we now have to solve the simultaneous equations:
$$
\begin{align}
2 &= \lambda 2x \tag{1} \\
2 &= \lambda 2y \tag{2} \\
x^2 + y^2 &= 4 \tag{3}  \\
\end{align}
$$
First we notice that $\lambda, x, y$ can not be zero otherwise it would violate 1 and 2.
Next we can simplify 1 to get $x = 1/ \lambda$ and 2 to get $y = 1/\lambda$ and substitute this into 3 to get:
$$
\begin{align}
\frac{1}{\lambda^2} + \frac{1}{\lambda^2} &= 4 \\
2 &= 4 \lambda^2 \\
\lambda &= \pm \frac{1}{\sqrt 2}\\
\end{align}
$$
This gives us that our maxima and minima occur at
$$
\begin{align}
x, y = \pm \sqrt 2
\end{align}
$$
### Multiple constraints (Not assessable)
If we have multiple constraint surfaces $g_i$ then our equation we have to solve turns into
$$
\begin{align}
\nabla f(\vec a) = \lambda_1 \nabla g_1(\vec a) + \lambda_2 \nabla g_2(\vec a) + \dots + \lambda_n \nabla g_n(\vec a)
\end{align}
$$
This is because now we have that $\nabla f(\vec a)$ is a linear combination of the $\nabla g_n(\vec a)$ constraints.

