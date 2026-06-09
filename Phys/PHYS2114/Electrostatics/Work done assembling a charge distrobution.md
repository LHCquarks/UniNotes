Given a distribution of desecrate charged particles we can consider reconstructing it particle by particle.
This is just
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
Thus the total sum becomes
$$
\begin{align}
W_{\text{Total}} &= \sum_{i = 0}^N\sum_{j = 0}^{i - 1} \frac{1}{4\pi\epsilon_0} \frac{q_i q_j}{r_{ji}}
\end{align}
$$
This expression is then equivalent to
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
## Continuous distributions
If we have a continuous distribution then our $q_i$ becomes a $dq$ and we have to sum over all of space. Further, the contribution of our $dq$'s to our $V_i$ is negligible therefore we have the formula
$$
\begin{align}
W &= \int V(\vec x) dq \\
&= \int V(\vec x)\rho(\vec x) d\tau \\
&= \int \epsilon_0 V(\nabla \cdot \vec E) d\tau \\
\end{align}
$$
Using integration by parts for vectors:
$$
\begin{align}
\int \nabla \cdot (f\vec A) d\tau &= \int f\nabla \vec A d \tau + \int(\vec A \cdot \nabla f) d\tau\\  
\int f \nabla \cdot \vec A d \tau &= -\int(\vec A \cdot \nabla f) d\tau + \oint f\vec A d\vec a
\end{align}
$$
We get
$$
\begin{align}
W &= -\epsilon_0\int \vec E \cdot \nabla V d\tau + \epsilon_0 \oint V \vec E \cdot d\vec A \\
W &= \epsilon_0\int \vec E \cdot \vec E d\tau + \epsilon_0 \oint V \vec E \cdot d\vec A \\
W &= \epsilon_0\int \vec E^2 d\tau + \epsilon_0 \oint V \vec E \cdot d\vec A \\
\end{align}
$$
Now, considering this integral as our integrating surface tends to infinity we get that $\oint V \vec E \cdot d \vec A$ goes to $0$ because $V \approx \frac{1}{r}$, $E \approx \frac{1}{r^2}$ and $d A \approx r^2$.
This leads to the expression
$$
\begin{align}
W &= \epsilon_0 \int_{\mathbb R^3} \vec E^2 d\tau
\end{align}
$$

**Note:** These formulas calculate the total energy taken to from each and every charge not just to bring all the charges together so for the case of two discrete particles this will give a different answer that the of the discrete formula.