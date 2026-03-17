## Critical points
We define **critical** points of a function $f: \Omega \rightarrow \mathbb R$ as points that satisfy:
- $\vec a$ is a stationary point so $\nabla f(\vec a) = \vec 0$
- $\vec a$ is on the boundary of $\Omega$ so that $\vec a \in \partial \Omega$
- $\vec a \in \text{Int}(\Omega)$ is a non-differentiable point on $\Omega$
## Global maxima and minima
For points on a **compact** set $\Omega$ we can guarantee that there exists a **global maximum** and **global minimum** for a function $f: \Omega \rightarrow \mathbb R$.

We can also guarantee all local and global maxima and minima occur at **critical** points of $f$.

Usually when finding these points we want to argue that our maxima can not be on the boundary of the function and there are no non-differentiable points of the interior of $\Omega$ so that all potential points occur when $\nabla f(\vec a) = \vec 0$.
### Classifying stationary points
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