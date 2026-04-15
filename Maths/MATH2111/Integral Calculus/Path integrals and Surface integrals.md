## Path integrals
Say we have a multivariable function that we want to integrate over a specific path as bellow. 
![[Pasted image 20260415154006.png]]
To do this we take our integral over the multivariable function $F(x, y)$ and substitute our parameterized curve $c(t)$ as so:
$$
\begin{align}
\int_c F(x, y) ds &= \int_a^b F(c(t)) |J_c(t)|dt \\
 &= \int_a^b F(c(t)) |c'(t)|dt \\
\end{align}
$$
Here $ds$ represents an infinitesimal displacement vector along the curve.

If we expand our $c(t)$ in terms of it's unit vectors to get $c(t) = x(t) \hat \imath  + y(t) \hat \jmath$ then we can write our equation as:
$$
\begin{align}
\int_c F(x, y) ds &= \int_a^b F(c(t)) |c'(t)|dt \\
&= \int_a^b F(x(t), y(t)) |(x'(t), y'(t))|dt \\
&= \int_a^b F(x(t), y(t)) \sqrt{(x'(t))^2 + (y'(t))^2}dt \\
&= \int_a^b F(x(t), y(t)) \sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2}dt \\
\end{align}
$$
These integrals can be used to solve things like
