Separation of variables is used to solve partial differential equations involving multiple variables.

## The technique
When we have some partial differential equation we assume that we have a solution of the form $V(x, y, z) = \sum_k X_k(x)Y_k(y)Z_k(z)$ and solve from there.

A standard method is as such:
1. Write the equation
2. Consider the symmetries of the setup allowing us to eliminate specific derivatives
3. Write down the boundary conditions
4. Write $V = \sum_k X_k(x)Y_k(y)Z)k(z)$
5. Plug in our new $V$ and divide both sides by $XYZ$
6. Pick constants such that $C_X + C_Y + C_Z = 0$

## An example
Say we have Laplace's equation:
$$
\begin{align}
\frac{\partial^2 V}{\partial x^2} +
\frac{\partial^2 V}{\partial y^2} +
\frac{\partial^2 V}{\partial z^2} = 0
\end{align}
$$
Then we assume $V = X(x)Y(y)Z(z)$ and substitute
$$
\begin{align}
YZ\frac{\partial^2 X}{\partial x^2} +
XZ\frac{\partial^2 Y}{\partial y^2} +
XY\frac{\partial^2 Z}{\partial z^2} = 0
\end{align}
$$
Dividing by $XYZ$ we get
$$
\begin{align}
\frac{1}{X}\frac{\partial^2 X}{\partial x^2} +
\frac{1}{Y}\frac{\partial^2 Y}{\partial y^2} +
\frac{1}{Z}\frac{\partial^2 Z}{\partial z^2} = 0
\end{align}
$$
Varying just $x$ tells me that $\frac{1}{X}\frac{\partial^2 X}{\partial x^2} + C_Y + C_Z = 0$ and so $\frac{1}{X}\frac{\partial^2 X}{\partial x^2} = C_X$. This holds for all $x, y, z$ by symmetry and so we have that
$$
\begin{align}
C_X + C_Y + C_Z = 0
\end{align}
$$
along with
$$
\begin{align}
\frac{d^2 X}{d x^2} = C_X X \\
\frac{d^2 Y}{d y^2} = C_Y Y \\
\frac{d^2 Z}{d z^2} = C_Z Z \\
\end{align}
$$
Now we just have to solve $\frac{d^2 X}{d x^2} = C_X X$.
