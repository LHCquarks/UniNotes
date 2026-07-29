Similar to the scalar field, we can expand the Biot-Savart law to produce a series in $\frac{1}{r^2}$ to aquire approximations for the vector field.

Starting from
$$
\begin{align}
\vec A(\vec r) &= \frac{\mu_0}{4\pi} \int\frac{\vec I}{\mathscr r}dl'
\end{align}
$$
and using the result derived for the scalar field that
$$
\begin{align}
\frac{1}{\mathscr r} &= \frac{1}{r}\sum_{n = 0}^\infty \left(\frac{r'}{r}\right)^nP_n(\cos \theta')
\end{align}
$$
We get the expression
$$
\begin{align}
\vec A(\vec r) &= \frac{\mu_0}{4\pi} \int\vec I \frac{1}{r}\sum_{n = 0}^\infty \left(\frac{r'}{r}\right)^nP_n(\cos \theta') dl' \\
&= \frac{\mu_0}{4\pi}  \sum_{n = 0}^\infty \frac{1}{r^{n + 1}}\int\vec I (r')^nP_n(\cos \theta') dl' \\
&= \frac{\mu_0}{4\pi}  \sum_{n = 0}^\infty \frac{\vec M_n}{r^{n + 1}} \\
\end{align}
$$
For $n = 0$ we have that
$$
\begin{align}
\vec M_0 &= \int\vec I (r')^0P_0(\cos \theta') dl' \\
&= \int\vec I dl' \\
&= 0
\end{align}
$$
for closed loops of current and thus the $n = 1$ term is the one we care about the most which is given by
$$
\begin{align}
\vec M_1 &= \int\vec I (r')^1P_1(\cos \theta') dl' \\
\vec M_1 &= \int\vec I r'\cos \theta' dl' \\
\vec M_1 &= I\vec a \times \hat r \\
\end{align}
$$
