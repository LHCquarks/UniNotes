Linear functions are functions of the form $f(z) = az$ for some $a\in \mathbb{C} \textbackslash 0$ 

If $a = c+id$ then we get
$$
\begin{align}
f(z) &= (c+id) (x+iy) \\
&= (cx - dy) + i(dx + cy)
\end{align}
$$
Note that this is the same as the matrix 
$$
\begin{align}
\begin{pmatrix}
c & -d \\
d & c
\end{pmatrix}
\end{align}
$$
Also note that
$$
\begin{align}
\begin{pmatrix}
c & -d \\
d & c
\end{pmatrix}
=
r
\begin{pmatrix}
\cos\theta & -\sin\theta \\
\sin\theta & \cos\theta
\end{pmatrix}
\end{align}
$$
Where
$$
\begin{align}
r &= \sqrt{c^2 + d^2} \\
\cos\theta &= \frac{c}{r} \\
\sin\theta &= \frac{d}{r}
\end{align}
$$

Which is the same as rotating the number by $\theta$ and scaling by $r$