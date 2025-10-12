We can represent all events by the space time vector $\begin{pmatrix}ct\\x_1\\x_2\\x_3\end{pmatrix}$ (also called a $4$-vector) encoding the events position and time off occurrence.

We then define the distance between any two points in spacetime as being the "proper time" aka the time elapsed for the object experiencing the two events through the use of the Metric Tensor $$M_{\mu, \nu} = \begin{pmatrix}
1 &0 &0 &0 \\ 0 &-1 &0&0 \\ 0&0&-1&0\\0&0&0&-1
\end{pmatrix}.$$
This gives us the equation that $S = \Delta t^2 - \Delta x_1^2 - \Delta x_2^2 - \Delta x_3^2$ where $S$ is the proper time. ![[Pasted image 20250809130229.png]]
Thus, by this definition, [[Lorentz transformations]] are all linear transformations that preserve this above rule about proper time

## Energy momentum vector
By differentiating the space time vector with respect to time we get the vector $\begin{pmatrix} c \\ v_1 \\ v_2 \\ v_3 \end{pmatrix}$ , which when we multiply with the rest mass of the object we get $\begin{pmatrix} mc \\ p_1 \\ p_2 \\ p_3 \end{pmatrix}$. Noticing that $E = mc^2$ for stationary particles and rearranging to get $mc = \frac{E}{c}$ we can substitute for $mc$ to arrive at the vector $\begin{pmatrix} E / c \\ p_1 \\ p_2 \\ p_3 \end{pmatrix}$ often called the momentum 4-vector.