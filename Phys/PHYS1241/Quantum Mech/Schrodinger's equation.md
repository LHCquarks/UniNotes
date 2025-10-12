Particles are described by the wave function $\Psi(x,t)$. To find the probability of finding a particle at $x$ at time $t$ you simply square the wave function $|\Psi(x,t)|^2$ giving the PDF for the particle.

To find how a particle's wave function evolves over time we use Schrodinger's equation: $$
i\hbar \frac{\partial \Psi}{\partial t} = \hat{H} \Psi \tag{1}
$$
where $\hat{H}$ is the Hamiltonian. 
***Note this is not relativistic***

## Derivation
Consider the equation $$H = E = \frac{\vec{p}^2}{2m} + V(\vec{x})$$
In quantum mechanics we make the following substitutions:
$$
\begin{align}
E &\rightarrow i\hbar \frac{\partial}{\partial t}\\
\vec{p} &\rightarrow \hat{P} = -i\hbar\vec{\nabla} \\
\vec{x} &\rightarrow \hat{X} = \vec{x}
\end{align}
$$
thus we get that for some function $\Psi(\vec{x},t)$ 
$$
\begin{align}
i\hbar\frac{\partial}{\partial t}\Psi(\vec{x}, t) &= \left(\frac{\hat{P}}{2m} + V(\vec{x})\right) \Psi(\vec{x}, t) \\
i\hbar\frac{\partial}{\partial t}\Psi(\vec{x}, t) &= \hat{H} \Psi(\vec{x}, t)
\end{align}
$$
## Solving it

We make the guess that $\Psi(\vec{x}, t) = \psi(\vec{x})e^{-iEt / \hbar}$. 
Plugging this into Schrodinger's equation we get:
$$
\begin{align}
i\hbar \frac{\partial}{\partial t} (\psi(\vec{x})e^{-Et / \hbar}) &= \hat{H}(\psi(\vec{x})e^{-Et / \hbar}) \\
-i\hbar E i/ \hbar \psi(\vec{x})e^{-Et / \hbar} &= \hat{H}(\psi(\vec{x})e^{-Et / \hbar}) \\
E\psi(\vec{x})e^{-Et / \hbar} &= \hat{H}(\psi(\vec{x})e^{-Et / \hbar}) \\
\end{align}
$$
assuming that $\hat{H}$ is time independent then we get that
$$\begin{align}
E\psi(\vec{x})&= \hat{H}\psi(\vec{x}) \\
\end{align}$$
Simplifying the Hamiltonian and simplifying for the 1d case
$$
\begin{align}
\hat{H} &= \frac{\hat{P}^2}{2m} + V(\vec{x}) \\
\hat{H} &= \frac{(-i\hbar\vec{\nabla})^2}{2m} + V(\vec{x}) \\
\hat{H} &= -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V(\vec{x}) \\
\hat{H} &= -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V(\vec{x}) \\
\end{align}
$$
and substituting it into the above equation we get
$$
\begin{align}
E\psi(x) &= \left(-\frac{\hbar^2}{2m} \frac{d^2}{d x^2} + V(x)\right) \psi(x). \tag{2} \\
\end{align}
$$
### Solving for a free particle
A free particle means that the potential is 0 everywhere so we get that
$$
\begin{align}
E\psi(x) &= -\frac{\hbar^2}{2m} \frac{d^2\psi}{dx^2} \\
\frac{d^2\psi}{d x^2} + \frac{E2m}{\hbar^2} \psi(x) &= 0 \\
\end{align}
$$
Substituting in $$
\begin{align} 
E &= \frac{p^2}{2m} \\
&= \frac{1}{2m} \left(\frac{h}{\lambda}\right)^2 \\
E &= \frac{\hbar^2k^2}{2m} \tag{3}
\end{align}
$$
we get
$$
\begin{align}
\frac{d^2\psi}{d x^2} + k^2 \psi(x) &= 0 \\
\end{align}
$$
By making the guess $\psi(x) = Ae^{\lambda x}$ we get

$$
\begin{align}
\lambda^2 + k^2 &= 0 \\
\lambda  &= \pm ik \\
\implies \psi(x) &= Ae^{ikx} + Be^{-ikx}.
\end{align}
$$
Finally, restoring the time dependence we get our solution for the 1d the Schrodinger equation is:
$$
\Psi(x,t) = (Ae^{ikx} + Be^{-ikx})e^{-iEt/\hbar} \tag{4}
$$
This solution is a combination of two waves propagating in opposite directions.
#### Investigating this solution
looking at the pdf for this function we get that $$
\begin{align} 
|\Psi(x,t)|^2 &= |Ae^{ikx}+Be^{-ikx}|^2|e^{-iEt/\hbar}|^2 \\
&= |Ae^{ikx}+Be^{-ikx}|^2 1^2 \\
&= |Ae^{ikx}+Be^{-ikx}|^2 \\
\end{align}
$$
for B = 0 we get 
$$
\begin{align} 
|\Psi(x,t)|^2 &= |Ae^{ikx}|^2 \\
&= A^2
\end{align}
$$
This means that the particle is uniformly distributed everywhere!
Now finding the momentum of the particle for this same case where $B = 0$ is as easy as applying the momentum operator
$$
\begin{align}
\hat{P}\Psi(x,t) &= -i\hbar\frac{\partial \Psi}{\partial x} \\
&= -i\hbar \frac{\partial}{\partial x}Ae^{ikx}e^{-iEt/\hbar} \\
&= -i\hbar e^{-iEt/\hbar} ikAe^{ikx} \\
&= k\hbar e^{-iEt/\hbar} Ae^{ikx} \\
&= k\hbar \Psi(x,t)
\end{align}
$$
This means that our wave function is an eigenvector for the momentum operator! The same thing applies for the Hamiltonian operator. Trust me bro

### Solving for an energy well
![[Pasted image 20250814203059.png]]
We start by recognising that region ii is just equation (4) .
Next, taking Schrodinger's equation $$i\hbar\frac{\partial}{\partial t}\Psi(x, t) = \left(\frac{\hat{P}}{2m} + V(x)\right) \Psi(x, t)$$

we notice that for this to hold when $V(x)=\infty$ $\Psi(x,t)$ must be zero. Now combining the solutions we get that 
$$
\begin{align}
\Psi(0, t) &= \Psi(0, t) \\
(Ae^{ik0} + Be^{-ik0})e^{-iEt/\hbar} &= 0 \\
0 &= A + B \\
A &= -B  \\
\end{align}
$$
and
$$
\begin{align}
\Psi(L, t) &= \Psi(L, t) \\
(Ae^{ikL} -Ae^{-ikL})e^{-iEt/\hbar} &= 0 \\
0 &= e^{ikL} - e^{-ikL} \\
e^{-ikL} &= e^{ikL} \\
1 &= e^{2ikL} \\
n2\pi &= 2k_nL \\
n\pi &= k_nL \\
k_n &= \frac{n\pi}{L}
\end{align}
$$
Combining these two we get 
$$
\begin{align}
\Psi(x, t) &= (Ae^{ik_nx} +Be^{-ik_nx})e^{-iEt/\hbar} \\
&= A(e^{in\pi x/L} - e^{-in\pi x/L})e^{-iEt/\hbar} \\
&= Ae^{-iEt/\hbar}2isin\left(\frac{n\pi x}{L}\right).\\
\end{align}
$$
Finding the PDF we get 
$$
\begin{align}
|\Psi(x,t)|^2 &= \left|A2ie^{-iEt/\hbar}sin\left(\frac{n\pi x}{L}\right)\right|^2 \\
&= 4A^2sin^2\left(\frac{n\pi x}{L}\right)
\end{align}
$$
Integrating from $0$ to $L$ we get the total probability to find the particle
$$
\begin{align}
1 &= \int_0^L 4A^2 sin^2\left(\frac{n\pi x}{L}\right)dx \\
&= \left[\frac{A^2L}{\pi n} \left( 2x - sin\left( \frac{2\pi n x}{L} \right) \right)\right]_0^L \\
&= \frac{A^2L}{\pi n} \left( 2L - sin(2\pi n) \right) \\
&= \frac{2A^2L^2}{\pi n} \\
A^2 &= \frac{\pi n}{2L^2} \\
A &= \pm\sqrt{\frac{\pi n}{2L^2}} \\
\end{align}
$$
Now we can substitute this back into the our equation for the wave function to get
$$
\Psi(x,t) = \pm\sqrt{\frac{\pi n}{2L^2}}e^{-iEt/\hbar}sin\left(\frac{n\pi x}{L}\right).
$$

### Finding the Energy
To find the energy we use equation (3) which gives us:
$$
\begin{align}
E &= \frac{\hbar^2k^2}{2m} \\
&= \frac{\hbar^2n^2\pi^2}{2mL^2} \\
&= \frac{h^2n^2\pi^2}{(2\pi)^2\cdot 2mL^2} \\
&= \frac{h^2}{8mL^2}n^2
\end{align}
$$

Using the energy operator we get
$$
\begin{align}
\hat{E}\Psi(x,t) &= i\hbar \frac{\partial}{\partial t}\left(\sqrt{\frac{\pi n}{2L^2}}e^{-iEt/\hbar}sin\left(\frac{n\pi x}{L}\right)\right) \\
&= i\hbar \sqrt{\frac{\pi n}{2L^2}} sin\left(\frac{n\pi x}{L}\right) \frac{\partial}{\partial t}\left(e^{-iEt/\hbar}\right) \\
&= i\hbar (-iE/\hbar) \sqrt{\frac{\pi n}{2L^2}} sin\left(\frac{n\pi x}{L}\right) e^{-iEt/\hbar} \\
&= E \sqrt{\frac{\pi n}{2L^2}} sin\left(\frac{n\pi x}{L}\right) e^{-iEt/\hbar} \\
&= E \Psi(x,t) \\
\end{align}
$$
Wow, Our wave function is an eigenvector for the energy operator!

### Fully expanded
$$
\Huge{\Psi(x,t) = \pm\sqrt{\frac{\pi n}{2L^2}}e^{-i\frac{h\pi n^2}{4mL^2}}sin\left(\frac{n\pi x}{L}\right)}.
$$
Note that the $\pm$ represents different spins of the particle whilst $n$ represents the different energy levels that the particle can take
