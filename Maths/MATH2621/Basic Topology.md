## $|w + z|$ 

### Equality
#### Lemma
For all complex numbers $w$ and $z$ 
$$|w + z|^2 = |w|^2 + 2Re(w\bar{z}) + |z|^2 \tag{1}$$
#### Proof
$$\begin{align}
|w+z|^2 &= (w + z)\overline{(w + z)} \\
&=(w+z)(\bar w + \bar z) \\
&= w\bar w + w\bar z + z\bar w + z\bar z \\
&= |w|^2 + w\bar{z} + \overline{(w \bar z)} + |z|^2 \\
&= |w|^2 + 2Re(w\bar z) + |z|^2
\end{align}$$
#### Note
For regular vectors we get that $|w+z|^2 = |w|^2 + 2\langle w, z \rangle + |z|^2$ which is very similar to the above.
This means that the inner product of a complex number is $$\langle w,z\rangle = 2Re(w\bar z)$$
### Triangle inequality
$$|w+z| \leq |w| + |z|\tag{2}$$ 

### The Circle inequality
#### Lemma
For all complex numbers $w$ and $z$
$$||w|-|z|| \leq |w-z| \tag{3}$$
#### Proof
$$
\begin{align}
w&=(w-z)+z \\
|w| &= |(w-z) + z| \\
|w| &\leq |w - z| + |z| \tag{2} \\
|w| - |z| &\leq |w - z|
\end{align}
$$
Swapping $w$ and $z$ in the above working we get
$$
\begin{align}
|z|-|w| &\leq |z-w| \\
|z|-|w| &\leq |w - z| \\
\end{align}
$$
Combining we get that
$$
\begin{align}
||w|-|z|| &= \text{max}\{|w| - |z|, |z| - |w|\} \\
&\leq |w - z|
\end{align}
$$
#### Visual Proof
If we imagine $w$ and $z$ on the complex plane we get ![[Pasted image 20250914091657.png]]
where $|z|$ and $|w|$ are radii of different circles. $|w-z|$ reaches a minimum when $w$ and $z$ are in the same direction in which case $||w|-|z||  =  |w-z|$. Because $||w|-|z||$ is constant as $w$ and $z$ move around the circle and $|w-z|$ only increases we get $$||w|-|z|| \leq |w-z|$$
## Balls
### The open ball
#### Definition
The open ball (also called a disk) centered at $z_0$ with radius $\epsilon$ is denoted as $\text{B}(z_0, \epsilon)$ and is defined as the set $$
\text{B}(z_0, \epsilon) = \{z \in \mathbb{C}: |z - z_0| < \epsilon\} \tag{4}
$$
![[Pasted image 20250914210108.png]]
### The punctured open ball
#### Definition
The punctured open ball is an open ball excluding $z = z_0$ hence it is defined as
$$\text{B}\degree(z_0, \epsilon) = \{z\in\mathbb{C}:0<|z-z_0|<\epsilon\}$$
![[Pasted image 20250914210338.png]]

## Relationship between points and a subset
For a subset of the complex plane $S$ and a point in the complex plane $z_0$.
### Interior point
A point is on the interior of a subset $S$ if there exists a small enough $\epsilon$ such that the ball around $z_0$ with radius $\epsilon$ is a subset of $S$. In other words, a point is considered to be on the interior of a subset if there exists an $\epsilon$ such that
$$
\text{B}(z_0,\epsilon) \cap S = \text{B}(z_0, \epsilon)
$$
### Exterior point
A point is on the exterior of a subset $S$ if there exists a small enough $\epsilon$ such that the ball around $z_0$ with radius $\epsilon$ has no common elements with $S$. In other words, a point is considered to be on the exterior of a subset if there exists an $\epsilon$ such that 
$$
\text{B}(z_0, \epsilon) \cap S = \emptyset
$$
### Boundary point
A point is on the boundary of a subset $S$ if it is neither an internal point nor an exterior point.
### Diagram
<span style="color:green">In green is an interior point</span>
<span style="color:red">In red is an exterior point</span>
<span style="color:orange">In orange is a boundary point</span>
![[Pasted image 20250914210853.png]]
## Types of sets
Suppose $S$ is a set
### Open Set
A set is open if all it's points are interior points. Open sets are generally denoted with $\Omega$ and is what we mostly focus on in complex analysis.![[Pasted image 20250915105618.png]]
### Closed Set
A set is closed if it contains all it's boundary points or equivalently, it's complement $\mathbb{C} / S$ is open![[Pasted image 20250915105709.png]]
### Closure of a Set
The Closure of the set $S$ is the set containing $S$ and all of the boundary points of $S$
### Bounded Set
A set is bounded if there exists a large enough $R\in \mathbb{R}^+$ such that $S \subseteq \text{B}(0, R)$
### Compact Set
A set is compact if it is both bounded and closed
### Region
A set is a region if it is an open set with some, none or all of it's boundary points
### Note
A set does not have to be open or closed but rather can be both, one of or none of them. An example is the complex plane which does not have any boundary points so is both closed and open!

## Arcs
### Polygonal arcs
Polygonal arcs are a finite sequence of directed line segments where one end point of one line is the start of the next![[Pasted image 20250915105944.png]]
### Simple closed polygonal arcs
A Simple closed polygonal arc is a polygonal arc that does not cross itself (simple) and who's final point of it's last segment is the start of the first segment![[Pasted image 20250915110053.png]]
### The complement of a simple closed polygonal arc
The complement of a simple closed polygonal arc is split into two segments, the bounded interior and unbounded exterior

## Polygonally Path connectedness
Let $X\subseteq \mathbb{C}$.
1. The Set $X$ is polygonally path connected if any two points in $X$ can be connected by a polygonal arc that is fully contained within $X$ ![[Pasted image 20250915110804.png]]
2. The Set $X$ is simply polygonally connected if it is polygonally path-connected and the interior of every simple closed polygonal arc in $X$ is lies in $X$. That is "$X$ has no holes" ![[Pasted image 20250916120805.png]]![[Pasted image 20250916120828.png]]
3. The Set $X$ is a domain if it is open and polygonally path connected
![[Pasted image 20250916122723.png]]
