Laplace's equation states $\nabla^2 V = 0$. This is applicable whenever we are outside of a source and is thus useful in many places.
## Averages
In one dimension Laplace's equation is quite trivial with:
$$
\begin{align}
\frac{\partial ^2 V}{\partial x^2} = 0
\end{align}
$$
and thus the solutions take the form
$$
\begin{align}
V(x) = mx+c
\end{align}
$$
Linear equations are quite special and exhibit a property that seems quite obscure but as we will see generalize nicely. This property is that the value of $V$ at a specific point $x_0$ is equal to the average of all points a distance $R$ away for all possible $R$.
$$
\begin{align}
V(x_0) = \frac{1}{2} \left[V(x_0 + R) + V(x_0 - R)\right]
\end{align}
$$

This property also holds for the 2d case were "all the points a distance $R$ away" is circle:
$$
\begin{align}
V(\vec x_0) = \frac{1}{2\pi R}\oint_C V(\vec x) ds
\end{align}
$$
where $C$ is the circle centered at $x_0$ with a radius $R$.

Finally, This property also holds for the 3d case where
$$
\begin{align}
V(\vec x_0) = \frac{1}{4\pi R^2} \oint_S V(\vec x) dA
\end{align}
$$
## Maxima and minima
Assume there is a local minima of $V$ at the point $\vec x_0$. For this to be the case, from the definition of the limit there must be a small enough ball of radius $R$ where all points in that ball evaluate to a value less than $V(x_0)$ ie $\forall x \in \text{B}(x_0, R), V(x) < V(x_0)$.

Now imagine integrating along the boundary of that ball. Dubbing the surface area of the ball $A$, by the ML lemma we get the inequality:
$$
\begin{align}
\frac{1}{A}\oint_{\partial B} V(\vec x) d\vec x &< V(x_0) \frac{A}{A} \\
V(x_0) & < V(x_0)
\end{align}
$$
which is obviously a contradiction so $V(x)$ **has no minima**.

Further, the same logic holds for all maxima of $V(x)$ with the argument breaking down on the boundary of the surface that $V$ is defined on. Thus:

$V(x)$ **has no maxima / minima** on the interior of the region $V(x)$ is defined on.
## Uniqueness theorem
Laplace's equation has many solutions but in the real world voltage only takes one value at some point so what information do we need to know to take our many solutions and filter them to just one?

Laplace's uniqueness theorem states that the solution to Laplace's equation $\nabla^2 V$ is across some volume $\mathcal V$ is uniquely determined if $V$ is specified along the boundary surface $\partial \mathcal V$. 
## Solving Laplace's equation
Because of the above uniqueness theorem, if we can find a single solution to Laplace's equation we have solved it for all solutions and thus we can make use of strong techniques that may not always come up with solutions such as **Separation of variables**.
