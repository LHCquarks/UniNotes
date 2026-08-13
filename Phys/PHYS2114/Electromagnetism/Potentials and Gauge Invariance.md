## Potentials
Take Faraday's equation and the no-magnetic monopoles law.
$$
\begin{align}
\vec \nabla \times \vec E &= -\frac{\partial \vec B}{\partial t} \tag {1}\\ 
\vec \nabla \cdot \vec B &= 0 \tag{2}
\end{align}
$$
$(2)$ implies that there exists functions $\vec A$ such that $\vec B = \vec \nabla \times \vec A$ and thus for a scalar function $\varphi$  we get:
$$
\begin{align}
\vec \nabla \times \vec E &= -\frac{\partial }{\partial t} \left(\vec \nabla \times \vec A\right) \tag{1}\\
\vec \nabla \times \vec E &= \vec \nabla \times \left(-\frac{\partial \vec A}{\partial t} \right)\\
\vec E &= -\vec \nabla \varphi-\frac{\partial \vec A}{\partial t}\\

\end{align}
$$
These two functions are called the **Vector Potential** and **Scalar Potential** respectively. With these two functions Faraday's law and the no magnetic monopoles law become trivial and we only get two truly dynamic Maxwell equations:
$$
\begin{align}
\vec \nabla \cdot \vec E &= \frac{\rho}{\epsilon_0} \\
\implies -\nabla ^2 \varphi -\partial _t \left(\vec \nabla \cdot \vec A\right) &= \frac{\rho}{\epsilon_0}\\
\vec \nabla \times \vec B &= \mu_0 \vec J + \mu_0 \epsilon_0 \frac{\partial \vec E}{\partial t} \\
\implies \mu_0\vec J &= \left(\mu_0\epsilon_0\partial^2_t\vec A - \nabla^2\vec A\right) + \vec \nabla \left(\vec \nabla \cdot \vec A + \mu_0\epsilon_0 \partial _t \varphi \right)
\end{align}
$$
## Gauge transformation and Gauge invariance
Given an arbitrary scalar function $g$ we can transform our potentials via
$$
\begin{align}
\varphi &\rightarrow \varphi' = \varphi - \frac{\partial g}{\partial t} \\
\vec A &\rightarrow \vec A' = \vec A + \vec \nabla g
\end{align}
$$
This is called a gauge transformation however if we compute our electric and magnetic fields we get:
$$
\begin{align}
\vec B' &= \vec \nabla  \times \vec A' \\
&= \vec \nabla \times \left(\vec A + \vec \nabla g\right) \\
&= \vec \nabla \times \vec A + \vec \nabla \times \vec \nabla g \\
&= \vec B + 0 \\
&= \vec B \\
\vec E' &= -\vec \nabla \varphi' - \frac{\partial \vec A'}{\partial t} \\
&= -\vec \nabla \left(\varphi - \frac{\partial g}{\partial t}\right) - \frac{\partial}{\partial t}\left(\vec A + \vec \nabla g\right) \\
&= -\vec \nabla \varphi +\vec \nabla \frac{\partial g}{\partial t} - \frac{\partial\vec A}{\partial t} - \vec \nabla \frac{\partial g}{\partial t} \\
&= -\vec \nabla \varphi - \frac{\partial\vec A}{\partial t} \\
&= \vec E\\
\end{align}
$$
Because $\vec B$ and $\vec E$ are 'real' whilst our potentials can not ever be directly measured this means they are arbitrary and we can chose $g$ to be whatever we want to simplify the physics and the math. This property is called **Gauge Invariance** 
## Common Gauges
When working with potentials it is often useful to select a gauge and role with it. The two most common gauges are:
- The Coulomb Gauge
- The Lorentz Gauge

### Coulomb Gauge
The Coulomb gauge satisfies the equation
$$
\begin{align}
\vec \nabla \cdot \vec A &= 0
\end{align}
$$
This simplifies a lot of things namely Gauss's law where we now get
$$
\begin{align}
\vec E &= -\vec \nabla \varphi \\
-\nabla^2\varphi &= \frac{\rho}{\epsilon_0}
\end{align}
$$
And the coulomb solution becomes valid:
$$
\begin{align}
\varphi(\vec r) &= \frac{1}{4\pi\epsilon_0}\int\frac{\rho(\vec r')}{\mathscr r} d\tau'
\end{align}
$$
### Lorentz gauge
The Lorentz gauge is defined by the condition
$$
\begin{align}
\vec \nabla \cdot \vec A + \mu_0\epsilon_0\partial_t\varphi = 0
\end{align}
$$
In this gauge the dynamic Maxwell equations become symmetric
$$
\begin{align}
-\nabla ^2 \varphi -\partial _t \left(\vec \nabla \cdot \vec A\right) &= \frac{\rho}{\epsilon_0}\\
\rightarrow -\nabla ^2 \varphi +\partial _t \left(\mu_0\epsilon_0\partial_t\varphi\right) &= \frac{\rho}{\epsilon_0}\\
\left(\mu_0\epsilon_0 \partial_t^2 -\nabla ^2 \right)\varphi &= \frac{\rho}{\epsilon_0}\\ \\

\left(\mu_0\epsilon_0\partial^2_t\vec A - \nabla^2\vec A\right) + \vec \nabla \left(\vec \nabla \cdot \vec A + \mu_0\epsilon_0 \partial _t \varphi \right) &= \mu_0\vec J \\ 
\rightarrow 
\left(\mu_0\epsilon_0\partial^2_t - \nabla^2\right)\vec A + \vec \nabla 0 &= \mu_0\vec J \\ 
\left(\mu_0\epsilon_0\partial^2_t - \nabla^2\right)\vec A &= \mu_0\vec J \\ 
\end{align}
$$
This Gauge is Lorentz invariant and thus is really useful when analyzing relativistic phenomena.