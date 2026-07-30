Given a 4-vector $x$ we can construct an invariant scalar $s^2$ by taking the scalar product of the vector with itself:
$$
\begin{align}
s^2 &= x^\mu x_\mu = (ct)^2 - x^2 - y^2 - z^2
\end{align}
$$
This invariant is called the "line segment" of a vector and is very important in SR.

Importantly, because $s^2$ is invariant we this value does not change between reference frames (this is obvious but is reiterating explicitly because it is so important).
## Light Cones
Assuming that $s^2 = 0$ we then find that
$$
\begin{align}
0 &= (ct)^2 - x^2 - y^2 - z^2
\end{align}
$$
which is the equation for a cone that makes an angle of $45^\circ$ with the $ct$ axis
![[Pasted image 20260730135730.png]]
Because we know that only light travels with $s^2 = 0$ this is called a light cone. Within the cone $s^2 > 0$ and outside $s^2 < 0$ and because Lorentz transforms preserve this metric points may never move between these regions.
## Absolute time and space
Consider all events such that $s^2 > 0$, that implies that $(ct)^2 > r^2$ for all observers. If we were to then say that $t > 0$ then it is easy to see that for all observers $t > 0$ and thus the event will still occur after the event $Q$ no matter what. Due to this fact, these events are said to be in the **absolute future** of the event $Q$.

Similarly, if an event starts out in the past of $Q$ it will remain in the past of $Q$ to all reference frames and thus is said to be in the **absolute past** of $Q$. Together, all of these events are referred to as **timelike** events.

An exterior point $P$ of the light cone however has $s^2 < 0$ and it can be proven that there exists reference frames such that:
- $Q$ happens before $P$
- $Q$ happens simultaneously to $P$
- $Q$ happens after $P$
Which means that logically $Q$ can not be influenced by $P$.

These sorts of events are called **spacelike**
## Proper time
Take a timelike event with respect to the origin that has the attached 4-vector $x$. Also assume that the space component of the 4-vector is entirely in the $x$-direction such that $x = (x^0, x^1, 0, 0)$.

We can then consider a new frame that has velocity $v = \frac{x^1}{x^0}c$. In this frame we get $\beta = \frac{x^1}{x^0}$ and the Lorentz transform produces:
$$
\begin{align}
\pmatrix{(x')^0 \\ (x')^1} &= \gamma \pmatrix{1 & - \frac{x^1}{x^0} \\ -\frac{x^1}{x^0} & 1} \pmatrix{x^0 \\ x^1}\\
(x')^1 &= \gamma(-\frac{x^1}{x^0}x^0 + x^1) \\
&= \gamma(0)\\
&= 0
\end{align}
$$
Thus any timelike vector can be transformed into a purely time vector $x' = ((x')^0,0, 0, 0)$ and $s^2 = t_0^2$. For this reason the linesegment is sometimes referred to as the **proper time**.