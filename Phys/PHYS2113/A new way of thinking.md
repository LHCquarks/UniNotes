In higher level physics Classical Mechanics is the theory of finding the trajectory of a system described by a set of **generalized coordinates** through a **configuration space**.
## Generalized coordinates
Given a system we can describe it's state with a set of variables $q^\alpha$ where $\alpha$ ranges from $1-N$.

These variables are called **generalized coordinates** and live in a coordinate space $\mathcal M$ something we will refer to as the **configuration space**.

The **generalized coordinates** of our systems can be our normal $x, y, z$ coordinates or they could be more abstract.

Within this course we will be working with the minimum number of coordinates necessary to describe the system.

We will also only consider **Holonomic** systems where the number of degrees of freedom is equal to the dimension of our **configuration space**
## Physics with generalized coordinates
Whilst Cartesian coordinates are great and fairly useful, we want to be able to work in more general coordinate systems so we can make use of unique symmetries.

To achieve this we want our <span style="color:red">laws of physics should not be dependent on a specific coordinate system</span>. This is the major advantage of the new formalism of classical we will develop in this subject.
## Old way of thinking
Newtonian mechanics can be summarized as such:

We are given a set of $N$ particles that in Cartesian coordinates have a position $\vec x_i(t)$.
We can also take $m\frac{d\vec {x_i}}{dt}$ which we call the momentum of the particle and will write as $\vec p_i(t)$.

Further, we have all the equations for forces between particles which depend only on $\vec x_i(t), \vec p_i(t), t$.
Finally, using Newton's 2nd law we can write a set of coupled ODEs:
$$
\begin{align}
m \ddot x_i(t) = \vec F_i(\vec x_j, \vec p_j, t)
\end{align}
$$
## Laplace's demon
It is known that all coupled ODEs like the ones in Newtonian mechanics all have a unique solution provided initial $\vec x_j, \vec p_j$'s at a time $t_0$ and thus Newtonian mechanics is deterministic.

In other words, if there was an entity that knew all the $\vec x_j$ and $\vec p_j$ at any given time to infinite precision they would be able to predict the future and past with perfect accuracy. This entity is know as "**Laplace's demon**" 
## Changing coordinates in Newtonian mechanics
Say we have a system described in a $\vec X$ coordinate system such that:
$$
\begin{align}
m \vec x_i(t) = \vec F_i(\vec x_j, \vec p_j, t)
\end{align}
$$
Then we will apply the transformation $\vec x' = R(t)\vec x + f(t)$. Solving for our old coordinate system we get:
$$
\begin{align}
\vec x &= R^{-1}(t) [\vec x' - \vec f(t)] \\
\vec{\dot x} &= \dot R^{-1}(t) [\vec x' - f(t)] + R^{-1}(t)\left[\vec{\dot x}'- \vec{\dot f}(t)\right] \\
\vec{\ddot x} &= \ddot R^{-1}(t) [\vec x' - f(t)] + \dot R^{-1}(t)\left[\vec{\dot x}'- \vec{\dot f}(t)\right] 
+ \dot R^{-1}(t)\left[\vec{\dot x}'- \vec{\dot f}(t)\right]
+ R^{-1}(t)\left[\vec{\ddot x}'- \vec{\ddot f}(t)\right]
\\
m\vec{\ddot x} &= m\ddot R^{-1}(t) [\vec x' - f(t)] + 2m\dot R^{-1}(t)\left[\vec{\dot x}'- \vec{\dot f}(t)\right] 
+ mR^{-1}(t)\left[\vec{\ddot x}'- \vec{\ddot f}(t)\right]
\\
\end{align}
$$
We can then substitute this into our prior equations of motion to get a new set of equations of motion:
$$
\begin{align}
m\ddot R^{-1}(t) [\vec x' - f(t)] + 2m\dot R^{-1}(t)\left[\vec{\dot x}'- \vec{\dot f}(t)\right] 
+ mR^{-1}(t)\left[\vec{\ddot x}'- \vec{\ddot f}(t)\right] =
\vec F_i(\vec x_j, \vec p_j, t) \\
mR^{-1}(t)\left[\vec{\ddot x}'- \vec{\ddot f}(t)\right] =
\vec F_i(\vec x_j, \vec p_j, t)  -
m\ddot R^{-1}(t) [\vec x' - f(t)] - 2m\dot R^{-1}(t)\left[\vec{\dot x}'- \vec{\dot f}(t)\right]
\\
mR^{-1}(t)\vec{\ddot x}' =
\vec F_i(\vec x_j, \vec p_j, t)  -
m\ddot R^{-1}(t) [\vec x' - f(t)] - 2m\dot R^{-1}(t)\left[\vec{\dot x}'- \vec{\dot f}(t)\right] + mR^{-1}(t)\vec{\ddot f}(t)
\\
m\vec{\ddot x}' =
R(t)\vec F_i(\vec x_j, \vec p_j, t)  -
mR(t)\ddot R^{-1}(t) [\vec x' - f(t)] - 2mR(t)\dot R^{-1}(t)\left[\vec{\dot x}'- \vec{\dot f}(t)\right] + m\vec{\ddot f}(t)
\\
\end{align}
$$
Thus our new force looks very different. The only scenario where we do not pick up any new forces is when $R(t)$ is constant and $\vec {\ddot f}(t) = \vec0$. Transformations that respect these conditions are called **Inertial frames**.

