Consider a general function $f(q_i, p_i, t)$ in phase space. Now consider the time derivative of this function
$$
\begin{align}
\frac{df}{dt} &= \sum_i \left(\frac{\partial f}{\partial q_i}\dot q_i
+ \frac{\partial f}{\partial p_i} \dot p_i\right)
+ \frac{\partial f}{\partial t} \\
&= \sum_i \left(\frac{\partial f}{\partial q_i}\frac{\partial \mathcal H}{\partial p_i}
- \frac{\partial f}{\partial p_i} \frac{\partial \mathcal H}{\partial q_i}\right)
+ \frac{\partial f}{\partial t} \\
\end{align}
$$

We can then define this new symbol as the Poisson bracket:
$$
\begin{align}
\left\{f, g\right\}
&= \sum_i \left(\frac{\partial f}{\partial q_i}\frac{\partial \mathcal g}{\partial p_i}
- \frac{\partial f}{\partial p_i} \frac{\partial \mathcal g}{\partial q_i}\right)
\end{align}
$$
then our time derivative becomes
$$
\begin{align}
\frac{df}{dt} &= \{f, \mathcal H\} + \frac{\partial f}{\partial t}
\end{align}
$$
This is essentially an equation of motion for $f$ in a system governed by $\mathcal H$ and thus you can find an equation of motion for any quantity that you want.
## Properties
The Poisson bracket is:
- antisymetric
$$
\begin{align}
\{f, g\} = - \{g, f\}
\end{align}
$$
- bilinear
$$
\begin{align}
\{\lambda f + \mu g, h\} &= \lambda \{f, h\} + \mu\{g, h\} 
\end{align}
$$
- Fulfills the Jacobi identity
$$
\begin{align}
\left \{f, \{g, h\}\right \}
+ \left \{h, \{f, g\}\right \}
+ \left \{g, \{h, f\}\right \}
&= 0
\end{align}
$$
These are the same properties as the commutators in quantum mechanics. 
## Poisson brak
###
Lets consider the Poisson brackets of a bunch of different variables:
$$
\begin{align}
\dot p_i 
&= \{p_i, \mathcal H\} + \frac{\partial p_i}{\partial t} \\
&= \sum_j \left(\frac{\partial p_i}{\partial q_j}\frac{\partial \mathcal H}{\partial p_j}
- \frac{\partial p_i}{\partial p_j} \frac{\partial \mathcal H}{\partial q_j}\right)
 + 0 \\
&= \sum_j \left(0\frac{\partial \mathcal H}{\partial p_j}
- \delta_{ij} \frac{\partial \mathcal H}{\partial q_j}\right)\\
&= -\frac{\partial \mathcal H}{\partial q_i}\\
\end{align}
$$
And similarly we can recover Hamilton's equations for $\dot q_i$.

