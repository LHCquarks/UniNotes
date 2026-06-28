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
7. Solve the resultant differential equations for $X, Y, Z$
8. Apply boundary conditions

As you might notice we say our solution is the sum of a bunch of different products of functions $V(x, y, z) = \sum_k X_k(x)Y_k(y)Z_k(z)$ however we proceed to solve for only the case of $V = XYZ$. We do this because the solution set for $V$ often does not decrease too much if we assert that $X_kY_kZ_k$ also satisfies our differential equation and such situations produce far easier results.
## Example
Suppose we have a setup where:

Two infinite grounded metal plates lie parallel to the $xz$ plane, one at $y = 0$ and the other at $y = a$. The left end at $x = 0$ is closed off with an infinite strip insulated from the two plates that maintains a specific potential $V_0(y)$. Find the potential in the region $x > 0, 0 < y < a$ .

![[Pasted image 20260615142208.png]]
We start with Laplace's equation:
$$
\begin{align}
\frac{\partial^2 V}{\partial x^2} + \frac{\partial^2 V}{\partial y^2} + \frac{\partial^2 V}{\partial z^2} = 0
\end{align}
$$
We notice that $z$ is symmetric and so $V$ should not vary in the $z$ direction so the respective partial should be $0$, hence we can get rid of it.
Next we assume that $V = \sum\limits_{n=1}^\infty X_n(x)Y_n(y)$ and consider only one of the terms that we also assert solves Laplace's equation so that
$$
\begin{align}
Y\frac{d^2 X}{d x^2} +
X\frac{d^2 Y}{d y^2} 
&= 0 \\
\frac{1}{X}\frac{d^2 X}{d x^2} +
\frac{1}{Y}\frac{d^2 Y}{d y^2} 
&= 0 \\
\end{align}
$$
only varying $x$ gives $\frac{1}{X}\frac{\partial^2 X}{\partial x^2} = c_x$ and vice versa for $y$. Further, we get that $c_x + c_y = 0$ and substituting $c_x = k^2$ we get $c_y = -k^2$.
Thus our two differential equations become
$$
\begin{align}
\frac{d^2 X}{d x^2} &= k^2X \\
\frac{d^2 Y}{d y^2} &= -k^2Y \\
\end{align}
$$
which when solved give
$$
\begin{align}
X(x) &= Ae^{kx} + Be^{-kx} \\
Y(y) &= C\sin(ky) + D\cos(ky) \\
\end{align}
$$
Time to sub in the boundary conditions. Subbing in $y = 0$ we get
$$
\begin{align}
0 &= C\sin(0) + D\cos(0) \\
0 &= D
\end{align}
$$
Then $y = a$
$$
\begin{align}
0 &= C\sin(ka) \\
ka &= n\pi \\
k &= \frac{n\pi}{a}
\end{align}
$$
Then $x = \infty$ means that $A = 0$. We can then not solve the final boundary condition without the full series and so our expression becomes
$$
\begin{align}
V = \sum_{n=0}^\infty Be^{n\pi x/a} C\sin\left(\frac{n\pi}{a}y\right)
\end{align}
$$
We can then take $C_n = BC$ then sub in $x = 0$ to assert our boundary condition for $V_0$
$$
\begin{align}
V_0(y) = \sum_{n = 0}^\infty C_n \sin\left(\frac{n\pi}{a} y\right)
\end{align}
$$
This is then just a problem of finding the Fourier coefficients which can be done via an overlap integral.

By the uniqueness theorem this is the only solution to Laplace's equation and thus we are done.
