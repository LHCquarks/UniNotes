Consider a circuit with an inductor and a power source:
![[Pasted image 20260804074533.png]]
We know that
$$
\begin{align}
V(t) = L \frac{dI}{dt}
\end{align}
$$
and so assuming a square wave voltage pulse of height $V_0$ and time $\tau$ we get our final current as $I_0 = \frac{V_0 \tau}{L}$
![[Pasted image 20260804075056.png]]
Now, the work done by this setup is:
$$
\begin{align}
W &= \int_0^\tau V(t)I(t)dt \\
&= \int_0^\tau V_0 \frac{V_0t}{L}dt \\
&= \frac{V_0^2 \tau^2}{2L} \\
&= \frac{LI_0^2}{2}
\end{align}
$$
The work in this setup goes into the magnetic.

Now lets consider the specifics of an ideal conductor:

Assume an infinitely long solenoid made out of a non-resistive metal. It is known that in this solenoid 
$$
\begin{align}
B &= \frac{\mu_0 I N}{l} \\
L &= \mu_0 N^2 \frac{A}{l}
\end{align}
$$
Then the total work is
$$
\begin{align}
W &= \frac{L I^2_0}{2} \\
&= \frac{\mu_0N^2A}{l} \left(\frac{Bl}{\mu_0 N}\right)^2 \frac{1}{2} \\
&= \frac{\mu_0N^2A}{l} \frac{B^2l^2}{\mu_0^2 N^2} \frac{1}{2} \\
&= \frac{B^2Al}{2\mu_0} \\
\end{align}
$$
Because the volume is given by $Al$ we get the energy density of our field:
$$
\begin{align}
W_B &= \frac{B^2}{2\mu_0}
\end{align}
$$
Compare this to the electric field:
$$
\begin{align}
W_E &= \frac{\epsilon_0 E^2}{2}
\end{align}
$$
## Pressure of magnetic field
Consider a magnetic field of $B = 40$T, the pressure of the magnetic field is given by the derivative of the energy wrt the volume
$$
\begin{align}
p &= \frac{\partial E}{\partial \tau} \\
&= \frac{B^2}{2\mu_0} \\
&= \frac{1600}{2 \times4\pi \times 10^{-7}} \\
&\approx \frac{200}{3} \times 10^{7} \\
&\approx 6.67 \times 10^{8} \text{ pa}
\end{align}
$$
which is way to large for any material on earth to withstand and hence we can not make magnets of this strength in the real world.