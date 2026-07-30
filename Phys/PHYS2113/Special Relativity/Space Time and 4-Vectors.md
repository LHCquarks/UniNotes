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
## 4-Vectors
We can package coordinates in our space time into a vector $x = (x^0, x^1, x^2, x^3)$. This is called a 4-vector.

We refer to the elements of our vectors generally with $x^\mu$ where any Greek letter $\mu$ can range from $0\dots3$ inclusive and very rarely refer to the vector itself. This way everything is commutative as they are just numbers. 

Further, if we want to only refer to the space coordinates of our vector we can use roman indexes such as $i$ like so: $x^i$

4-Vectors are 4 numbers that transform between inertial reference frames using a Lorentz transform $\Lambda$. Note that these possible Lorentz transforms include both rotations and boosts. If $\mathcal S'$ is moving along a vector $\vec u$ in $\mathcal S$ we first have to rotate $\mathcal S$ so the x-axis aligns with $u$, then apply the boost, and rotate back so that the x-axis aligns with the x'-axis: $\Lambda_{R, 2} \Lambda_B \Lambda_{R, 1}$. This is provably equivalent to doing a single rotation and boost $\Lambda_R \Lambda_B$.

### Lorentz Scalars
A Lorentz Scalar / 4-Scalar is a quantity that is invariant under Lorentz transforms.
Examples include line elements / proper time and suitably defined mass.
## Scalar product
In normal space $\vec a \cdot \vec b = a_xb_x + a_yb_y + a_zb_z$ is invariant under rotation and we would like something similar with 4-Vectors. 

To achieve this we need to "flip" the sign of the space coordinates so that
$$
\begin{align}
a\cdot b &= a^0b^0 - a^1b^1 - a^2b^2 - a^3b^3
\end{align}
$$
To do this in our 4-Vector notation we introduce $x_\mu$ as apposed to $x^\mu$ which is our $x^\mu$ times something called the metric.
$$
\begin{align}
x_\mu &= \sum_{\nu}\delta^\mu_\nu x^\nu
\end{align}
$$
As a reminder $x_\mu$ is just a number and so is $\delta^\mu_\nu x^\nu$. Einstein got very sick of writing summation notation when dealing with these sorts of things so he developed Einstein summation notation in which if we have two indices (one in the upper and one in the lower part) then the summation is implicit so our formula becomes
$$
\begin{align}
x_\mu = \delta_\nu^\mu x^\nu
\end{align}
$$
Very nice but what is $\delta^\mu_\nu$? Well this is a special tensor to our spacetime given by
$$
\begin{align}
\delta^\mu_\nu &= 
\begin{cases}
0 & \mu \not = \nu \\
1 & \mu = \nu = 0 \\
-1 & \mu = \nu = 1\dots 3 \\
\end{cases}
\end{align}
$$
Finally, we can write our scalar product of our 4-vectors $a, b$ as
$$
\begin{align}
a^\mu b_\mu &= \sum_\mu a^\mu \delta^\mu_\nu x^\nu
\end{align}
$$
