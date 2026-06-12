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

