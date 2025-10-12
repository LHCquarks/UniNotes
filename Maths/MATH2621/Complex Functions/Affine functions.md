Affine functions are like linear functions add some constant. This is seen in it's definition:

An Affine function $f: \mathbb{C} \rightarrow \mathbb{C}$ is a function of the form $f(z) = az + b$ where $a\in\mathbb{C}\textbackslash 0, b \in \mathbb{C}$.

Note that all linear functions are Affine functions but not vise versa.

Similar to linear functions they have a matrix representation:
Taking $a = c + id$ and $b = e + if$ we get:
$$
\begin{align}
\begin{pmatrix}
x \\ y
\end{pmatrix}
\rightarrow
\begin{pmatrix}
c & -d \\ d & c
\end{pmatrix}
\begin{pmatrix}
x \\ y
\end{pmatrix}
+
\begin{pmatrix}
e \\ f
\end{pmatrix}
\end{align}
$$
## Properties
- If you apply an affine function to a line it will result in another line
- If you apply an affine function to a circle it will remain a circle
- The inverse of an affine map is another affine map
- A grid remains a grid under an affine function