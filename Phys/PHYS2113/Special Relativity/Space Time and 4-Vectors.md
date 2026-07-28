## Symmetric Lorentz transform
The Lorentz transform is effectively a linear map of our time and space coordinates:
$$
\begin{align}
t' &= \gamma \left(t - v\frac{x}{c^2}\right) \\
x' &= \gamma \left(x - vt\right) \\
y' &= y \\
z' &= z \\
\end{align}
$$
We can make this more symmetric via placing strategic $c's$:
$$
\begin{align}
ct' &= \gamma \left(ct - v\frac{x}{c}\right) \\
x' &= \gamma \left(x - \frac{vct}{c}\right) \\
ct' &= \gamma \left(ct - \beta x\right) \\
x' &= \gamma \left(x - \beta ct\right) \\
\end{align}
$$
We can then package all this into vectors and a matrix:
$$
\begin{align}
\pmatrix{ct' \\ x' \\ y' \\ z'} &= 
\pmatrix{
\gamma & -\beta\gamma & 0 & 0 \\
-\beta\gamma & \gamma & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
}
\pmatrix{ct \\ x \\ y\\ z}
\end{align}
$$
This was first discovered by Minkowski. Often, instead of $(t,x,y,z)$ we write $(x^0, x^1, x^2, x^3)$ treating time very similarly as a space coordinate.
## The Lorentz transform is a sort of rotation
If we define an "angle" $\phi$ such that $\beta = \tanh(\phi)$ then our Lorentz transform becomes:
$$
\begin{align}
x'^0 &= \cosh \phi x^0 - \sinh\phi x^1 \\
x'^1 &= -\sinh \phi x^0 + \cosh \phi x^1
\end{align}
$$
Which is just a rotation using hyperbolic trig functions instead of the normal trig functions. In this sense applying a Lorentz transform is just a hyperbolic rotation
![[Pasted image 20260728145704.png]]
This map of space and time is called space-time and shows that it is hyperbolic in the $x^0$ axis.