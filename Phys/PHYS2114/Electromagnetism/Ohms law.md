## Ohm's law
Ohm, through lots of maths showed that in a conductor the following relation approximately holds:
$$
\begin{align}
\vec J(\vec r) &= \sigma \vec E(\vec r)
\end{align}
$$
where:
- $\vec J$ is the volume current density
- $\sigma$  is the electric conductivity of the conductor (a constant that varies with time)
- $\vec E$ is the electric field at that point within the conductor
### Other ohm's law
The above ohms law is what chud physics students use but how does this relate to the chud engineering students law? 
$$
\begin{align}
V = IR
\end{align}
$$
We will derive this law for a straight conducting wire but the value for $R$ is different for different geometries of wires.

We start the derivation by assuming a conductor where $\vec J$ flows along the direction of the wire ($z$ direction) and the boundary conditions are $z = 0 \implies V = 0, z = L \implies V = V_0$.

Because $\vec J = \sigma \vec E$, we get that $\vec E$ must also be directed along the length of the wire and thus $V$ only varies along the $z$ direction thus by Laplace's equation:
$$
\begin{align}
\frac{\partial^2 V}{\partial x^2} + \frac{\partial^2 V}{\partial y^2} + \frac{\partial^2 V}{\partial z^2} &= 0 \\
\frac{d^2 V}{d z^2} &= 0 \\
\frac{d V}{d z} &= A \\
V(z) &= Az + B \\
V(0) = 0&= B \\
V(L) = V_0&= AL \\
V(z) &= \frac{V_0}{L}z
\end{align}
$$
To then find the current we first find the electric field and use ohm's law to find current density:
$$
\begin{align}
\vec E &= -\nabla V \\
&= -\frac{V_0}{L}\hat k \\
\vec J &= -\sigma \frac{V_0}{L} \hat k \\
I &= \int \vec J\cdot d\vec A \\
&= \int J dA \\
&= \sigma\frac{V_0}{L}\int dA \\
&= \frac{\sigma A}{L} V_0 \\
V &= \frac{L}{\sigma A} I \\
\end{align}
$$
This is just the chud eng ohms law with $R = \frac{L}{\sigma A}$.
### Resistivity
Because there are multiple standards in emag due to history there is another constant
$$
\begin{align}
\rho &= \frac{1}{\sigma}
\end{align}
$$
called the resistivity of the material. Some values for the resistivity of materials at $T = 20^\circ$ are bellow

| Material         | $\rho$                |
| ---------------- | --------------------- |
| Silver           | $1.59\times 10^{-8}$  |
| Copper           | $1.68 \times 10^{-8}$ |
| Lead             | $22 \times 10^{-8}$   |
| Gallium Arsenide | $1$                   |
| Silicon          | $100$                 |
| Diamond          | $10^{12}-10^{19}$     |
| Glass            | $10^{9}-10^{13}$      |
## Power
Because normally $P = \vec J \cdot \vec E$ we get that according to Ohm's law:
$$
\begin{align}
P = \sigma E^2
\end{align}
$$
## Drude formula
The resistivity of a material is caused by impurities "blocking" an electron's path
![[Pasted image 20260801121705.png]]
Here we know that the electron's mean free path is given by $l = v\tau$ 
Note that because $\vec v$ is not always in the direction of $\vec E$ Ohm's law is not valid on these microscopic distances and is only valid on scales of $\Delta r > l$.

Further, using $F=ma$ we can find the average velocity of the electron:
$$
\begin{align}
m\dot{\vec v} &= e\vec E \\
\vec v &= \vec v_0 + \frac{e}{m}\vec E t \\
\braket{\vec v} &= \braket{\vec v_0} + \braket{\frac{e}{m}\vec E t} \\
&= 0 + \frac{e}{m}\vec E \braket{t} \\
&= \frac{e}{m}\vec E \tau \\
\end{align}
$$
We know that $\vec J = ne\braket{\vec v}$ where $n$ is the number of electrons per $m^3$. Substituting this in to Ohm's law we get
$$
\begin{align}
\vec J &= \frac{ne^2\tau}{m} \vec E \\
\end{align}
$$
Thus we have a formula for $\sigma$:
$$
\begin{align}
\sigma &= \frac{ne^2\tau}{m}
\end{align}
$$
This is called the Drude formula.