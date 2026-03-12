To find the best polynomial approximation of our function, similar to the $1d$ case we set the derivatives of our polynomial to be equal to our function.
## Up to the 2nd derivative
### $2d$ input space
Taking the same form as our 1d taylor polynomial we find the 2d polynomial of the form:
$$
\begin{align}
P(x, y) &= f(a, b) + f_{x}(a, b)(x - a) + f_y (a, b) (y - b) \\ &+ \frac{1}{2}(f_{xx} (a, b) (x - a)^2 + 2f_{xy}(a, b) (x - a)(y - b) + f_{yy}(a,b)(y - b)^2
\end{align}
$$
Now this is equivalent to the matrix product:
$$
\begin{align}
P(x, y) = f(a, b) + \nabla f(a, b)\cdot \pmatrix{x - a \\ y - b} + \frac{1}{2} \pmatrix{x - a & y - a} \pmatrix{f_{xx}(a, b) & f_{xy}(a, b) \\ f_{yx}(a, b) & f_{yy}(a, b)} \pmatrix{x-a \\ y - b}
\end{align}
$$
You can check up to the 2nd partial derivatives are all equivalent to the same partials of $f$ 
### $nd$ input space
The 2nd order Taylor polynomial of $f$ around $\vec a \in \mathbb R^n$ evaluated at $\vec{x} \in \mathbb R^n$ is given by:
$$
\begin{align}
P(\vec{x}) = f(\vec{a}) + \nabla f(\vec{a}) \cdot (\vec v - \vec a) + \frac{1}{2} (\vec v - \vec a)^T 
\pmatrix{
f_{x_1 x_1}(\vec{a}) & f_{x_1x_2}(\vec{a}) & \dots & f_{x_1 x_n}(\vec a) \\
f_{x_2 x_1}(\vec{a}) & f_{x_2x_2}(\vec{a}) & \dots & f_{x_2 x_n}(\vec a) \\
\vdots \ \ \ \ \ \ & \vdots \ \ \ \ \ \  & \ddots & \vdots \ \ \ \ \ \ \\
f_{x_n x_1}(\vec{a}) & f_{x_nx_2}(\vec{a}) & \dots & f_{x_n x_n}(\vec a) \\
} (\vec{v} - \vec{a})
\end{align}
$$
This big matrix is called the **Hessian** matrix and is normally written as $H_f(\vec a)$. It is defined as above so that $[H_f(\vec a)]_{i,j} = f_{x_i, x_j}(\vec a)$ 

