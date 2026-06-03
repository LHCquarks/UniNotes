## Basic optimization
Given a function $f(x)$ we already know how to find it's maximum and minimum:
- solve $f'(x) = 0$
- test for $f''(x_0)$ to find the nature of the turning point
And we even know how to do this for the multivariable case and even with constraints with Lagrange multipliers.
## The Goal
The goal of the calculus of variations is to find a function $f(x)$ that extreme-izes an integral:
If we have
$$
\begin{align}
I[f] = \int_a^b f(x) ds
\end{align}
$$
then we want
$$
\begin{align}
\frac{dI}{df} = 0
\end{align}
$$
## An example
Lets consider the problem of finding the shortest path between two points.

Lets take an arbitrary function $f(x)$ which will represent our path. Now, the infinitesimal arclength of the path is given by:
$$
\begin{align}
dL &= \sqrt{dx^2 + dy^2} \\
&= \sqrt{dx^2 + df^2} \\
&= \sqrt{dx^2 + df^2} \frac{dx}{dx}\\
&= \sqrt{\left(\frac{dx}{dx}\right)^2 + \left(\frac{df}{dx}\right)^2} dx\\
&= \sqrt{1 + \left(\frac{df}{dx}\right)^2} dx\\
\end{align}
$$
Now integrating to find the shortest path we are met with the integral:
$$
\begin{align}
L[f] = \int_a^b \sqrt{1 + \left(\frac{df}{dx}\right)^2} dx
\end{align}
$$
This is where the calculus of variations would come in useful.

This can also be packaged up in perhaps a nicer way as:
$$
\begin{align}
L[f] = \int_a^b df
\end{align}
$$
where in this scenario $f$ is a peramaterisation of the path.
## The solution
Take the integral:
$$
\begin{align}
I[y] &= \int_{p_1}^{p_2}f(y(x), y'(x), x) dx
\end{align}
$$
and assume we have found a function $y$ that minimizes $I$. Then if we were to add a little wobble to the function it would no longer be a minimum. Mathematically, we define a new function by adding a "wobble function" to our original solution as shown below:
$$
\begin{align}
\mathcal Y(x) &= y(x) + \eta(x)
\end{align}
$$
Obviously for $\mathcal Y(x)$ to still be a valid path it still need to go through $p_1, p_2$ and as such $\eta(p_1) = \eta(p_2) = 0$. We also know
$$
\begin{align}
I[\mathcal Y] > I[y]
\end{align}
$$
What we are now going to do is redefine our $I$ to be a function of a regular old variable instead so that we can employ our preexisting calculus. To do this we are going to say that:
$$
\begin{align}
\mathcal Y(x) = y(x) + \alpha \eta(x)
\end{align}
$$
Then we will redefine $I$ to be
$$
\begin{align}
I(\alpha) &= \int_{p_1}^{p_2}f(\mathcal Y(x), \mathcal Y'(x), x) dx \\
&= \int_{p_1}^{p_2}f(y(x) + \alpha \eta(x), y'(x) + \alpha \eta'(x), x) dx
\end{align}
$$
Now we know that $I$ is minimized when $\alpha = 0$ and as such we can write
$$
\begin{align}
I'(0) = 0
\end{align}
$$
But from above we have an expression for $I'$
$$
\begin{align}
I'(\alpha) &= \int_{p_1}^{p_2} \frac{d}{d\alpha} f(\mathcal Y(x), \mathcal Y'(x), x) dx \\
&= \int_{p_1}^{p_2} \frac{\partial f}{\partial \mathcal Y} \frac{\partial \mathcal Y}{\partial \alpha} +\frac{\partial f}{\partial \mathcal Y'} \frac{\partial \mathcal Y'}{\partial \alpha} dx \\
&= \int_{p_1}^{p_2} \eta(x)\frac{\partial f}{\partial \mathcal Y} +\eta '(x)\frac{\partial f}{\partial \mathcal Y'} dx \\
\end{align}
$$
Now inspecting the second term we can integrate it by parts to get
$$
\begin{align}
\int_{p_1}^{p_2} \eta'(x)\frac{\partial f}{\partial \mathcal Y'} dx &=
\left[\eta(x) \frac{\partial f}{\partial \mathcal Y'}\right]_{p_1}^{p_2} - \int_{p_1}^{p_2} \eta(x) \frac{d}{dx}\frac{\partial f}{\partial \mathcal Y'} dx \\
&=0 - \int_{p_1}^{p_2} \eta(x) \frac{d}{dx}\frac{\partial f}{\partial \mathcal Y'} dx

\end{align}
$$
Thus it follows
$$
\begin{align}
I'(\alpha) &= \int_{p_1}^{p_2} \eta(x)\frac{\partial f}{\partial \mathcal Y} -\eta(x) \frac{d}{dx}\frac{\partial f}{\partial \mathcal Y'}dx \\
I'(\alpha) &= \int_{p_1}^{p_2} \eta(x)\left[\frac{\partial f}{\partial \mathcal Y} - \frac{d}{dx}\frac{\partial f}{\partial \mathcal Y'}\right]dx \\
I'(0) &= \int_{p_1}^{p_2} \eta(x)\left[\frac{\partial f}{\partial \mathcal Y} - \frac{d}{dx}\frac{\partial f}{\partial \mathcal Y'}\right]dx \\
0 &= \int_{p_1}^{p_2} \eta(x)\left[\frac{\partial f}{\partial \mathcal Y} - \frac{d}{dx}\frac{\partial f}{\partial \mathcal Y'}\right]dx \\
\end{align}
$$
Now we assert that we want this to be true for every function $\eta(x)$ and thus we find that the expression in the square brackets must be $0$ and so we get the differential equation
$$
\begin{align}
0 = \frac{\partial f}{\partial \mathcal Y} - \frac{d}{dx}\frac{\partial f}{\partial \mathcal Y'}
\end{align}
$$
This equation is known as the Euler-Lagrange equation and will be central to Lagrangian mechanics.
## Back to our example
Looking back at our example
$$
\begin{align}
L[f] = \int_a^b \sqrt{1 + \left(\frac{df}{dx}\right)^2} dx
\end{align}
$$
Calling the intergrand $\mathcal L$ and renaming $f$ as $y$ we get:
$$
\begin{align}
\mathcal L = \sqrt{1 + \left(y'\right)^2}
\end{align}
$$
To minimize L we need to satisfy the EL equation:
$$
\begin{align}
\frac{\partial \mathcal L}{\partial y} - \frac{d}{dx}\frac{\partial \mathcal L}{\partial y'} &= 0 \\
0 - \frac{d}{dx}\frac{y'}{\sqrt{1 + (y')^2}} &= 0 \\
\frac{d}{dx}\frac{y'}{\sqrt{1 + (y')^2}} &= 0 \\
\frac{y'}{\sqrt{1 + (y')^2}} &= C \\
y' &= C\sqrt{1 + (y')^2} \\
(y')^2 &= C^2[1 + (y')^2] \\
(y')^2 &= C^2 + C^2(y')^2 \\
(y')^2 (1 - C^2)&= C^2 \\
y' &=\sqrt{\frac{C^2}{1 - C^2}} \\
y(x) &=\sqrt{\frac{C^2}{1 - C^2}}x + c \\
y(x) &=mx + c \\
\end{align}
$$
Thus the shortest distance between to points is a strait line
## The physics form of EL equation
Given:
$$
\begin{align}
A = \int_a^b \mathcal L(q_i, \dot q_i, t) dt
\end{align}
$$
To minimize $A$ We get the set of differential equations
$$
\begin{align}
\frac{\partial \mathcal L}{\partial q_i} = \frac{d}{dt}\frac{\partial \mathcal L}{\partial \dot q_i}
\end{align}
$$
This formula is the foundation of Lagranian mechanics.