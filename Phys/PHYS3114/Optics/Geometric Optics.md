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
And thus we have that light travels in a straight line if $n$ is constant. Another question we could ask is what is the index of refraction required to make light travel in a parabola?:
$$
\begin{align}
y(x) &= x^2 \\
y'(x) &= 2x \\
y''(x) &= 2 \\
\frac{\partial n}{\partial y} &= \frac{\partial n}{\partial x} 2x + \frac{2n}{1 + 4x^2}
\end{align}
$$
Using seperation of variables $n(x, y) = X(x), Y(y)$ gives:
$$
\begin{align}
X \frac{dY}{dy} &= 2x Y\frac{dX}{dx} + \frac{2XY}{1 + 4x^2} \\
\frac{1}{Y} \frac{dY}{dy} &= \frac{2x}{X}\frac{dX}{dx} + \frac{2}{1 + 4x^2} \\
\end{align}
$$
<% tp.file.cursor(2) %>
