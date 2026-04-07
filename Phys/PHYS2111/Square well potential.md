## The infinite square well
### Setup
Take a particle trapped in a box with the potential energy given by the function:
$$
\begin{align}
V(x) &= 
\begin{cases}
0 & 0 \le x \le a \\
\infty & \text{elsewhere}
\end{cases}
\end{align}
$$
It is safe to assume that outside the box the particle is not present.
### The solution
First start by noticing that $V(x)$ is time independent so we can employ the time independent Schrodinger equation.

We set $\hat H$ to be $\frac{\hat p^2}{2m} + V(x)$ which inside the box gives $\hat H = \frac{\hat p^2}{2m}$

Thus to find the eigenstates we simply need to solve:
$$
\begin{align}
\frac{\hat p^2}{2m} \psi(x) &= E_n \psi(x) \\
-\hbar^2\frac{\partial^2\psi}{\partial x^2} &= 2mE_n \psi(x) \\
\frac{\partial^2\psi}{\partial x^2} &= -\frac{2mE_n}{\hbar^2} \psi(x) \\
\end{align}
$$
Defining $k^2 = \frac{2mE_n}{\hbar^2}$ we recognize this differential equation and solve it through the technique of knowing the answer giving:
$$
\begin{align}
\psi(x) = A\sin(kx) + B\cos(kx)
\end{align}
$$
Now by the setup we know that $\psi(0) = 0, \psi(a) = 0$ and thus we get that:
$$
\begin{align}
0 &= A\sin(k0) + B\cos(k0) \\
0 &= B, \\
0 &= A\sin(ka) \\
0 &= \sin(ka) \\
ka &= n\pi, &n\in \mathbb Z
\end{align}
$$
And thus $k = \frac{n\pi}{a}$ whilst $B = 0$.
Normalizing we get:
$$
\begin{align}
1 &= \int_0^a |A|^2 \sin^2(kx) dx \\
&= |A|^2 \int_0^a \frac{1}{2}\left(1 - \cos(2kx)\right) dx \\
&= \frac{|A|^2}{2} \left[x - \frac{\sin(2kx)}{2k}\right]_0^a \\
&= \frac{|A|^2}{2} \left[a - \frac{\sin(2ka)}{2k}\right] \\
&= \frac{|A|^2}{2} \left[a - 0\right] \\
|A|^2 &= \frac{2}{a} 
\end{align}
$$
Because phase does not matter we will chose a phase of $0$ so that $A = \sqrt{\frac{2}{a}}$.
Now we can also set our two expressions for $k$ equal to find:
$$
\begin{align}
\left(\frac{n\pi}{a}\right)^2 &= k^2 = \frac{2mE_n}{\hbar^2} \\
E_n &= \frac{\hbar^2 n^2 \pi^2}{2m}
\end{align}
$$
Finally, combining with the time part of the Schrodinger equation we get our stationary states to be:
$$
\begin{align}
\Psi_n(x, t) &= \sqrt{\frac{2}{a}}\exp\left(-i\frac{\hbar n^2 \pi^2}{2m}t\right) \sin\left(\frac{n\pi}{a}x\right)
\end{align}
$$
## The finite square well
### The setup
Similarly to the infinite case we define the potential in the finite square well case to be:
$$
\begin{align}
V(x) &= 
\begin{cases}
0 & -a \le x \le a \\
V_0 & \text{elsewhere}
\end{cases}
\end{align}
$$
We will also only consider the bound states where $0 \le E \le V_0$.
Finally, this time we can not assume that outside the well the wave function is zero.
### The solution
For inside the well we have the same scenario as above thus we find:
$$
\begin{align}
\psi(x) &= A\sin(kx) + B\cos(kx)
\end{align}
$$
For outside the well on the other hand we get:
$$
\begin{align}
-\frac{\hbar^2}{2m} \frac{\partial^2 \psi}{\partial x^2} + V_0\psi(x) &= E \psi(x) \\
-\frac{\hbar^2}{2m} \frac{\partial^2 \psi}{\partial x^2} &= (E - V_0)\psi(x) \\
\frac{\partial^2 \psi}{\partial x^2} &= -\frac{2m(E - V_0)}{\hbar^2} \psi(x) \\
\frac{\partial^2 \psi}{\partial x^2} &= \frac{2m(V_0 - E)}{\hbar^2} \psi(x) \\
\end{align}
$$
Defining $\beta^2 = \frac{2m(V_0 - E)}{\hbar^2}$ using the fact that $V_0 - E \ge 0$ we can then solve the above equation again by knowing the solution to give:
$$
\begin{align}
\psi(x) &= C e^{\beta x} + D e^{-\beta x}
\end{align}
$$
Asserting that $\psi$ is normalize-able gives that for $x < -a$, $D = 0$ and for $x > a$, $C = 0$.
Thus our equation is:
$$
\begin{align}
\psi(x) &= 
\begin{cases}
Ce^{\beta x} & x < -a \\
A\sin(kx) + B\cos(kx) & -a \le x \le a \\
De^{-\beta x} & a < x
\end{cases}
\end{align}
$$
Now, demanding that $\psi(x)$ is continuous at $x = -a, a$  and that $\psi(x)$ is continuously differentiable at $x = -a, a$ we get the $4$ equations:
$$
\begin{align}
C e^{-\beta a} &= -A\sin(ka) + B\cos(ka) \tag {1}\\
C \beta e^{-\beta a} &= Ak\cos(ka) + B\sin(ka) \tag {2}\\
D e^{-\beta a} &= A\sin(ka) + B\cos(ka) \tag {3}\\
-D \beta e^{-\beta a} &= Ak\cos(ka) - B\sin(ka) \tag {4}\\
\end{align}
$$
Adding and subtracting them gives:
$$
\begin{align}
(D + C) e^{-\beta a} &= 2B\cos(ka) \tag{1 + 3} \\
(D - C) e^{-\beta a} &= 2A\sin(ka) \tag{3 - 1} \\
(C - D) \beta e^{-\beta a} &= 2Ak\cos(ka) \tag{2 + 4} \\
(C + D) \beta e^{-\beta a} &= 2Bk\sin(ka) \tag{2 - 4} \\
\end{align}
$$
We can not then divide these equations out as we do not know there are zeros so instead we will consider the odd and even parts of the equations giving:
$$
\begin{align}
k\tan(ka) &= \beta \tag{even} \\
k\cot(ka) &= -\beta \tag{odd} \\
\end{align}
$$
Now, unfortunately this can not be solved analytically and so need to be solved graphically or numerically. To do this we need to add in one other piece of information which is:
$$
\begin{align}
k^2 + \beta^2 &= \frac{2mE}{\hbar^2} + (V_0 - E) \frac{2m}{\hbar^2} \\
k^2 + \beta^2 &= \frac{2mV_0}{\hbar^2} \\
\end{align}
$$
Where both equations intersect is where we have bounded solutions for our stationary state which we can then use to find $A, B, C, D$ and thus $\psi(x)$ and finally $\Psi(x, t)$
