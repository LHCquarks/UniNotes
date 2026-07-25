## Time Dilation
Consider two inertial frame, $\mathcal S, \mathcal S'$ where $\mathcal S$ is stationary at a station whilst $\mathcal S'$ is on a train moving with a constant velocity $v$. Also consider a light beam that is released from the bottom of the train, reflects off a mirror situated at the top of the train and then is detected at the bottom of the train. This light setup essentially functions as a clock as the light has a fixed speed.

We can then consider the elapsed time for the clock in both reference frames:
![[Pasted image 20260723133444.png]]
Whist frame $\mathcal S'$  sees the light go a distance $2L$ and thus $\Delta t' = \frac{2L}{c}$,  frame $\mathcal S$ observes the light taking a longer path given by
$$
\begin{align}
AB^2 &= AD^2 + DB^2 \\
(c\Delta t_{1/2})^2 &= (v\Delta t_{1/2})^2 + L^2\\
c^2\Delta t^2_{1/2} &= v^2\Delta t^2_{1/2} + L^2\\
(c^2 - v^2)\Delta t^2_{1/2} &= L^2\\
\Delta t^2_{1/2} &=\frac{L^2}{c^2 - v^2}\\
\frac{\Delta t^2}{4} &=\frac{L^2}{c^2}\frac{1}{1 - \frac{v^2}{c^2}}\\
\Delta t^2 &=\frac{4L^2}{c^2}\frac{1}{1 - \frac{v^2}{c^2}}\\
\Delta t^2 &=\frac{(\Delta t')^2}{1 - \frac{v^2}{c^2}}\\
\Delta t &=\frac{\Delta t'}{\sqrt{1 - \frac{v^2}{c^2}}}\\
\end{align}
$$
Thus the time between events changed between reference frames. This effect is known as **time dilation**, very weird.
## Proper time
The time dilation formula is
$$
\begin{align}
\Delta t = \gamma\Delta t'
\end{align}
$$
and if we do it the other way round we get
$$
\begin{align}
\Delta t' &= \gamma \Delta t
\end{align}
$$
This is concerning as according to both formulas the other frame experiences time slower than itself. The problem is that we are measuring two different things.

Equation 1 measures the time taken between two events that occur at $x = 0$ in the $\mathcal S'$ reference frame

Equation 2 measures the time taken between two events that occur at $x = 0$ in the $\mathcal S$ reference frame

Thus there is no contradiction. We have a special term for the time between two events from the perspective of a reference frame where both events occur at $x = 0$. This is called the **proper time** and is denoted by $\Delta t_0$. This is an invariant between all frames and so is quite useful.
## Length contraction
Similar to time, the distance between two events change depending on the reference frame. If in the $\mathcal S$ F.O.R both events happen at $t = 0$ then we get the formula
$$
\begin{align}
l' &= \frac{l}{\gamma}\\
\end{align}
$$
which means that length contracts between reference frames.
## Rest length
Similar to time dilation we can define the invariant quantity $l_0$ as the distance between two events in the reference frame in which both events occur at the same time. With this quantity we have the formula
$$
\begin{align}
l &= \frac{l_0}{\gamma}
\end{align}
$$
