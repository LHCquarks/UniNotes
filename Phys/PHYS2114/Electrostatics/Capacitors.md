Capacitors are simply two oppositely charged conductors separated by a distance so that they can not exchange charge.
## Capacitance
The capacitance of a capacitor is a measure of how much charge a capacitor can hold at a given voltage. If the charge on each conductor is $+Q$ and $-Q$ respectively and the voltage between them is $V$ then the capacitance is given as
$$
\begin{align}
C = \frac{Q}{V}
\end{align}
$$
## Parallel plates
Parallel plate capacitors are the default type. We assume they are akin to infinite plates so $\vec E$ is uniform between them and that they are at a distance $d$ away along with having a charge of $Q$ and an area of $A$.

The voltage between the plates is then defined as
$$
\begin{align}
V &= - \int_0^d\vec E \cdot d\vec s \\
&= - \int_0^d -\frac{\sigma}{\epsilon_0} ds \\
&= \frac{\sigma}{\epsilon_0} [s]^d_0 \\
&= \frac{\sigma d}{\epsilon_0} \\
&= \frac{Qd}{A\epsilon_0} \\
\end{align}
$$
Thus the capacitance of the parallel plates is
$$
\begin{align}
C &= \frac{Q}{V} \\
&= \frac{A\epsilon_0}{d}
\end{align}
$$
## Charging a capacitor
To charge a capacitor we can imagine moving charges from one plate to another individually. The work done to move a charge between two points is
$$
\begin{align}
W &= q V
\end{align}
$$
and thus to move our infinitesimal charge segment we have to do $dW = V dq$. Substituting in our expression for capacitance and integrating we find the total work done to charge the capacitor is
$$
\begin{align}
dW &= \frac{q}{C} dq \\
\int dW &= \int_0^Q \frac{q}{C} dq \\
W &= \left[ \frac{q^2}{2C}\right]^Q_0\\
&= \frac{Q^2}{2C}\\
\end{align}
$$
We can also rewrite this again with the definition of capacitance as
$$
\begin{align}
W = \frac{1}{2} C V^2
\end{align}
$$
