If we want to make even more approximations we can treat wave as a ray not as a wave. This is the basic assumption of geometric optics and was what was believed before the wave nature of light was known.

## Fermat's Principle
Fermat suggested that when going between two points light takes the path that minimizes the time taken between those two points. That is that the functional equation 
$$
\begin{align}
T[\vec s] &= \int dt \\
&= c\int n(\vec s) ds
\end{align}
$$
is minimized. To enforce this we often parameterize the curve as $\vec s = (x, y(x))$ and then use the Euler-Lagrange equations to get:
$$
\begin{align}
T[y] &= \int n(x, y) \sqrt{1 + (y')^2} dx \\
\frac{\partial \mathcal L}{\partial y} &= \frac{d}{dx}\left(\frac{\partial \mathcal L}{\partial y'}\right) \\
\sqrt{1 + (y')^2}\frac{\partial n}{\partial y}&=  \frac{d}{dx}\left(n(x, y)\frac{y'}{\sqrt{1 + (y')^2}}\right) \\
&= \left[\frac{\partial n}{\partial x} + \frac{\partial n}{\partial y} y'\right] \frac{y'}{\sqrt{1 + (y')^2}} + \left[\frac{y''}{\sqrt{1 + (y')^2} } - \frac{(y')^2y''}{(1 + (y')^2)^{3/2}}\right]n(x, y) \\
\frac{\partial n}{\partial y}&= \left[\frac{\partial n}{\partial x} + \frac{\partial n}{\partial y} y'\right] \frac{y'}{1 + (y')^2} + \left[y'' - \frac{(y')^2y''}{1 + (y')^2}\right]\frac{n(x, y)}{1 + (y')^2} \\
\left[1 + (y')^2\right]\frac{\partial n}{\partial y}&= \frac{\partial n}{\partial x}y' + \frac{\partial n}{\partial y} (y')^2 + \frac{y''n(x, y)}{1 + (y')^2} \\
\frac{\partial n}{\partial y}&= \frac{\partial n}{\partial x}y' + \frac{y''n(x, y)}{1 + (y')^2} \\
\end{align}
$$
This is a very interesting family of differential equations and describe geometric optics very well. For example if $n(x, y) = 1$ then we have:
$$
\begin{align}
0 &= \frac{y''}{1 + (y')^2} \\
y'' &= 0 \\
y &= mx + c
\end{align}
$$
And thus we have that light travels in a straight line if $n$ is constant.
### Silly little question I made
Another question we could ask is what is the index of refraction required to make light travel in a parabola?:
$$
\begin{align}
y(x) &= x^2 \\
y'(x) &= 2x \\
y''(x) &= 2 \\
\frac{\partial n}{\partial y} &= \frac{\partial n}{\partial x} 2x + \frac{2n}{1 + 4x^2}
\end{align}
$$
Using separation of variables $n(x, y) = X(x), Y(y)$ gives:
$$
\begin{align}
X \frac{dY}{dy} &= 2x Y\frac{dX}{dx} + \frac{2XY}{1 + 4x^2} \\
\frac{1}{Y} \frac{dY}{dy} &= \frac{2x}{X}\frac{dX}{dx} + \frac{2}{1 + 4x^2} \\
\end{align}
$$
These two sides must be constant so we get that $\frac{1}{Y}\frac{dY}{dy} = k$ and $\frac{2x}{X}\frac{dX}{dx} + \frac{2}{1 + 4x^2} = k$ for some constant $k$. Thus:
$$
\begin{align}
Y(y) &= Ae^{ky} \\
\frac{1}{X}\frac{dX}{dx} &= -\frac{1}{x(1 + 4x^2)} + \frac{k}{2x} \\
\int \frac{dX}{X} &= \int \frac{1}{x(1 + 4x^2)} + \frac{k}{2x}dx\\
\ln(X) + C &= \int \frac{1}{x} - \frac{4x}{1 + 4x^2}  + \frac{k}{2x}dx\\
\ln(X) &= \ln x - \frac{1}{2} \ln( 1 + 4x^2) + \frac{k}{2}\ln x + C\\
X(x) &= A e^{(k/2 + 1)\ln x - \frac{1}{2} \ln( 1 + 4x^2)}\\
&= A e^{\ln x^{k/2 + 1}}e^{-\ln\sqrt{ 1 + 4x^2}}\\
&= \frac{B x^{k/2+1}}{\sqrt{ 1 + 4x^2}} \\
\end{align}
$$
Then all we need to do is set a boundary condition for $n(x, y)$ to derive our form for $n(x, y)$ where:
$$
\begin{align}
n(x, y) &= \int_{-\infty}^\infty X_k(x) Y_k(y) dk \\
&= \int_{-\infty}^\infty \frac{B_k x^{k / 2 + 1}}{\sqrt{1 + 4 x^2}} A_ke^{ky} dk
\end{align}
$$
Lets set the boundary conditions:
$$
\begin{align}
n(x, \infty) &= 0 \\
n(x, -\infty) &= 0 \\
\end{align}
$$
The first of these says:
$$
\begin{align}
0 &= \int_{-\infty}^\infty \frac{B_k x^{k / 2 + 1}}{\sqrt{1 + 4 x^2}} A_k e^{k \infty} dk
\end{align}
$$
For $k > 0$ we have that $e^{k \infty} = \infty$ and thus $A_k = 0$. 
Similarly, using $n(x, -\infty) = 0$ we get that $A_k = 0$ for $k < 0$ leaving only $k = 0$. In this case we have that $Y_0(y) = A$ and thus $Y(k, y) = A\delta(k)$. 
This gives:
$$
\begin{align}
n(x, y) &= \int_{-\infty}^\infty \frac{B_k x^{k / 2 + 1}}{\sqrt{1 + 4 x^2}} A\delta(k) dk \\
&= A\frac{B_0 x^{0 / 2 + 1}}{\sqrt{1 + 4 x^2}} \\
&= A\frac{B_0 x}{\sqrt{1 + 4 x^2}} \\
&= C\frac{x}{\sqrt{1 + 4 x^2}} \\
\end{align}
$$
This is quite cool I think.
$$
\begin{align}
0 &= C\left[\frac{1}{\sqrt{1 + 4x^2}} - \frac{4x^2}{(1 + 4 x^2)^{3/2}}\right]y' + \frac{y''Cx}{(1 + (y')^2)\sqrt{1 + 4x^2}} \\
0 &= \frac{C}{\sqrt{1 + 4x^2}}\left[\frac{1}{1} - \frac{4x^2}{1 + 4 x^2}\right]y' + \frac{y''Cx}{(1 + (y')^2)\sqrt{1 + 4x^2}} \\
0 &= \frac{C}{\sqrt{1 + 4x^2}}\frac{1}{1 + 4x^2}y' + \frac{y''Cx}{(1 + (y')^2)\sqrt{1 + 4x^2}} \\
0 &= \frac{y'}{1 + 4x^2} + \frac{y''x}{1 + (y')^2} \\
0 &= \frac{(2x)}{1 + 4x^2} + \frac{(2)x}{1 + (2x)^2} \\
\end{align}
$$
## Eikonal Equation
A completely equivalent formulation of geometric optics is the Eikonal equation
$$
\begin{align}
\nabla S &= n\hat s
\end{align}
$$
Where:
- $S$ is the wave function
- $n$ is the index of refraction
- $\hat s$ is the normal to the wave front
## Thin lens theory
A thin lens consists of the intersection of two circles of radii $R_1, R_2$ and focuses rays of light that are aligned to the optical axis towards the focus. All incident rays aligned with the optical axis will pass through the focus (all be it it may be virtually).
![[Pasted image 20261024112232.png|367]]
The distance of the focus follows the thin lens equation:
$$
\begin{align}
\frac{1}{f} &= (n -1) \left[ \frac{1}{R_1} - \frac{1}{R_2}\right]
\end{align}
$$
Where:
- $f$ is the distance from the center of the lens to the focus
- $R_1$ is the radius of the left circle
- $R_2$ is the radius of the right circle
This equation has a few assumptions about the sign of the objects:
- $f$ is positive if it is to the right of the lens and negative if it is to the left
- $R_1$ is positive if the center of the circle lies to the right
- $R_2$ is positive if the center of the circle lies to the right

### Typical lenses
![[Pasted image 20261024124517.png]]
As an example, for a typical lens with both circles curving outward (the one in the diagram above) we get:
- $R_1$ is +itive
- $R_2$ is -itive
thus $f$ is positive and so lies to the right of the lens

![[Pasted image 20261024125012.png|443]]
We have:
- $R_1$ is -itive
- $R_2$ is +itive
Thus we conclude that $f$ is -itive and so lies to the left of the lens. In this senario the ray passes through the focus virtually (Tracing the ray backwards in a straight line gets you to the focus)
## Matrix methods
When a light ray interacts with a medium in geometric optics it either changes it's angle or it's height with everything being linear thanks to the small angle approximation.

Because everything is linear we can make heavy use of linear algebra to abstract away our methods and let computers do it easier.

We write the state of our light ray as:
$$
\begin{align}
\pmatrix{n \alpha \\ y}
\end{align}
$$
and all interfaces then become matrices that act on our ray vector, for instance:
#### Vertical medium
By Snell's law we have $n_2 \alpha_2 = n_1 \alpha_1$ and so our first part should not change and nor should our second part do our matrix is just the identity matrix:
$$
\begin{align}
M &= \pmatrix{1 & 0 \\ 0 & 1}
\end{align}
$$
#### Normal Traversal
If our ray is just normally traversing a medium of thickness $t$ we have that $y$ needs to change by $\alpha t$ and $n \alpha$ remains unchanged thus our matrix must be:
$$
\begin{align}
M &= \pmatrix{1 & 0 \\ \frac{t}{n} & 1}
\end{align}
$$
#### Lenses
It is given from on high that going through one side of a lens gives the matrix
$$
\begin{align}
M &= \pmatrix{1 & \frac{n_i - n_t}{R} \\ 0 &1}
\end{align}
$$

