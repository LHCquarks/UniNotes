Conductors are materials where the internal charges are free to move within the conductor.
## Electric field in conductors
If there were an electric field inside of a conductor then the charges within the conductor would be moved by that field to a place that "cancels out" that field thus the electric field **inside** a conductor is:
$$
\begin{align}
\vec E = 0
\end{align}
$$ and thus
$$
\begin{align}
\rho = 0
\end{align}
$$
inside the conductor. This is even true when conductors are placed in external electric fields.

This property tells us that all charges of a conductor lives on the surface of the conductor and so the surface charge density is non-zero $\sigma \not = 0$.

Further, a conductor must also be equipotential so that for any two points on the conductor
$$
\begin{align}
V(\vec a) = V(\vec b)
\end{align}
$$
A final note is that the electric field is always **perpendicular** to the surface of the conductor.
## Cavities in conductors
Consider a conductor with a cavity in it. If we were then to place a charge inside of the cavity and then take a Gaussian surface around the cavity (the inner purple Gaussian surface) we would find that the total charge enclosed by the surface has to be $Q_{\text{enc}} = 0$ by Gauss's law.
![[Pasted image 20260626112254.png]]
Then considering a Gaussian surface around the entire conductor we get that the total charge is once again $Q_{\text{enc}} = q$ and thus the conductor "communicates to the exterior world" the existence of the charge whist it remains ignorant on the inside of the conductor. 

Further, if there is no charge inside the cavity then there is no electric field inside of it no matter the external situation, for if there was an electric field line would have to "emerge" from the cavity wall and enter it again indicating that it also must be present within the conductor itself violating $\vec E = 0$ inside a conductor. This is the principle of Faraday cages and why you can not be electrocuted inside a car.
## The Electric field at the boundary of a conductor
It is known that the electric field across a charged surface has the equation:
$$
\begin{align}
\vec E_\text{above} - \vec E_\text{below} = \frac{\sigma}{\epsilon_0} \hat n
\end{align}
$$
Because we are considering a conductor we know that $\vec E_{\text{below}} = 0$ and thus $\vec E_{\text{above}} = \frac{\sigma}{\epsilon_0}\hat n$ just outside a conductor.

Further, this means that the voltage just above the surface of a conductor has the relation
$$
\begin{align}
\sigma &= -\epsilon_0\frac{\partial V}{\partial n}
\end{align}
$$
which is very useful for finding the surface charge density of a conductor when the voltage just above it is known
## Electrostatic pressure 
To find the pressure exerted on a conductor we first need to find the force on a patch of area of the conductor. Ordinarily we would be able to just use the electric field to find this force however, because the electric field at the surface of the conductor is discontinuous it is not obvious what value for the electric field we should use.

Consider a small patch on the conductor. The electric field on that patch is given by $\vec E_{\text{total}} = \vec E_{\text{patch}} + \vec E_{\text{other}}$. The force on the patch is given by $q\vec E_{\text{other}}$ so we would like to isolate for just $\vec E_{\text{other}}$. 

The discontinuity in $\vec E_{\text{total}}$ comes entirely from the patch itself and hence we are able to write that 
$$
\begin{align}
\vec E_{\text{above}} = \vec E_{\text{other}} + \frac{\sigma}{2\epsilon_0}\hat n \\
\vec E_{\text{below}} = \vec E_{\text{other}} - \frac{\sigma}{2\epsilon_0}\hat n \\
\end{align}
$$
We can now simply add the two equations to get
$$
\begin{align}
\vec E_{\text{other}} = \frac{1}{2}\left[\vec E_{\text{above}} + \vec E_{\text{below}}\right]
\end{align}
$$
Substituting in the values we found before we get that $\vec E_{\text{other}} = \frac{\sigma}{2\epsilon_0} \hat n$.

Now we find that the force for a small patch of area is just $F = A\frac{\sigma^2}{2\epsilon_0} \hat n$ and so the preasure on a conductor is $P = \frac{\sigma^2}{2\epsilon_0} = \frac{\epsilon_0}{2}E_{\text{above}}^2$.