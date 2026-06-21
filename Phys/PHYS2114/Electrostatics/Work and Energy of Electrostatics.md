## Work done to assemble a charge distribution
We can imagine starting with nothing and slowly assembling the charge distribution piece by piece by bring the particles together from infinity.

This gives
$$
\begin{align}
W_0 &= 0 \\
W_1 &= q_1 \frac{1}{4\pi\epsilon_0} \frac{q_0}{r_{01}}\\
W_2 &= \frac{q_2}{4\pi\epsilon_0} \left [ \frac{q_0}{r_{02}} + \frac{q_1}{r_{12}}\right]\\
W_3 &= \frac{q_3}{4\pi\epsilon_0} \left [ \frac{q_0}{r_{03}} + \frac{q_1}{r_{13}} + \frac{q_0}{r_{23}}\right]\\
\vdots \\
W_i &= \frac{q_i}{4\pi\epsilon_0} \sum_{j= 0}^{i - 1}\frac{q_j}{r_{ji}}\\
\end{align}
$$
Thus the total work done to assemble a discrete charge distribution is 
$$
\begin{align}
W_{\text{Total}} &= \sum_{i = 0}^N\sum_{j = 0}^{i - 1} \frac{1}{4\pi\epsilon_0} \frac{q_i q_j}{r_{ji}}
\end{align}
$$
which by extending the interior sum to all particles we get
$$
\begin{align}
W_{\text{Total}} &= \frac{1}{2} \sum_{i = 0}^N \left[\sum_{j = 0}^N\frac{1}{4\pi\epsilon}\frac{q_iq_j}{r_{ji}}\right]
\end{align}
$$
Where $j \not = i$. If we then define $V_i(\vec x)$ as the voltage at the point $\vec x$ omitting the contributions of particle $i$ we are able to write this as simply
$$
\begin{align}
W_{\text{Total}} &= \frac{1}{2}\sum_{i = 0}^N q_i V_i(\vec x_i)
\end{align}
$$
## Continuous case
For the continuous case we simply need to change the summation into an integral. We can also replace $V_i$ with just $V$ as the contribution of the infinitesimal charge is not significant enough.
$$
\begin{align}
W &= \frac{1}{2}\int V(\vec r) dq  \\
&= \frac{1}{2}\int V\rho d \tau  \\
\end{align}
$$
This is good and all but we can simplify it with some sneaky tricks. First we use the differential form of Gauss's law to write
$$
\begin{align}
W&= \frac{1}{2}\int \epsilon_0 V(\nabla \cdot \vec E) d\tau \\
\end{align}
$$
Now, using integration by parts for vectors:
$$
\begin{align}
\int \nabla \cdot (f\vec A) d\tau &= \int f\nabla \vec A d \tau + \int(\vec A \cdot \nabla f) d\tau\\  
\int f \nabla \cdot \vec A d \tau &= -\int(\vec A \cdot \nabla f) d\tau + \oint f\vec A d\vec a
\end{align}
$$
We get
$$
\begin{align}
W &= -\frac{1}{2}\epsilon_0\int \vec E \cdot \nabla V d\tau + \frac{1}{2}\epsilon_0 \oint V \vec E \cdot d\vec A \\
W &= \frac{1}{2}\epsilon_0\int \vec E \cdot \vec E d\tau + \frac{1}{2}\epsilon_0 \oint V \vec E \cdot d\vec A \\
W &= \frac{1}{2}\epsilon_0\int \vec E^2 d\tau + \frac{1}{2}\epsilon_0 \oint V \vec E \cdot d\vec A \\
\end{align}
$$
Finally considering this integral as our integrating surface tends to infinity we get that $\oint V \vec E \cdot d \vec A$ goes to $0$ because $V \approx \frac{1}{r}$, $E \approx \frac{1}{r^2}$ and $d A \approx r^2$.
This leads to the expression
$$
\begin{align}
W &= \frac{1}{2}\epsilon_0 \int_{\mathbb R^3} \vec E^2 d\tau
\end{align}
$$
## Discrepancies between continuous formula and discrete
As you might notice it is possible for the discrete formula to produce negative numbers whilst it is not for the continuous formula due to $\vec E^2$ always being positive. So what gives? As it turns out, they are both correct, whilst the discrete formula measures the amount of work required to assemble a set of pre-existing point charges the continuous formula find the energy required to assemble a set of charge from nothing.

It was constantly debated between physicists of the time where this energy is stored but in the words of Richard Feynman "Who cares? What is the meaning of such a question? ... If we restrict our self to electrostatics there is really no way to tell where the energy is located."