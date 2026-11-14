Consider a single point charge with motion $\vec r_q(t)$ so that $\rho(\vec r', \vec t') = q\delta(\vec r' - \vec r_q(t'))$. 
## Scalar potential
We can apply the exact same techniques that we used for dipoles to get to 
$$
\begin{align}
\frac{\rho(\vec r', t_r)}{R} 
&\approx \frac{1}{r}\left[\rho + \frac{1}{c}r'\dot \rho \cos \alpha\right] +\frac{r'}{r^2}\rho \cos \alpha -  \frac{1}{c}\frac{(r')^2}{r^2}\dot \rho\left[\frac{1}{2} - \cos^2 \alpha \right] \\
\end{align}
$$
but we already have a $\frac{\rho}{r}$ and a $\frac{\dot \rho}{r}$ term so the last to vanish in the limit leaving us with
$$
\begin{align}
\frac{\rho(\vec r', t_r)}{R} 
&\approx \frac{\rho}{r} + \frac{r'}{cr}\dot \rho \cos \alpha\\
\end{align}
$$
Thus our potential is:
$$
\begin{align}
\varphi(\vec r, t) &\approx \frac{1}{4\pi \epsilon_0}\int_{\mathbb R^3}\frac{\rho}{r} + \frac{r'}{cr}\dot \rho \cos \alpha d^3 r'\\
&\approx \frac{1}{4\pi\epsilon_0 r} \left[\int_{\mathbb R^3} \rho d^3 r' + \frac{1}{c}\int_{\mathbb R^3} r'\dot\rho \cos\alpha d^3 r'\right] \\
&\approx \frac{1}{4\pi\epsilon_0 r} \left[q + \frac{\dot p \cdot \hat r}{c}\right] \\
\end{align}
$$
## Vector potential
Our current is given by $q \dot r_q(t)$ and thus our current density is
$$
\begin{align}
\vec J (\vec r', t') &= q \dot r_q(t') \delta(\vec r' - \vec r_q(t'))
\end{align}
$$
We can then use our Green's function for the vector potential to get:
$$
\begin{align}
\vec A(\vec r, t) &= \int \frac{\vec J (\vec r', t_r)}{R} d^3 r' \\
\end{align}
$$
Now, we can apply the exact same arguments as with the dipole expansion for the $\rho$ case to get:
$$
\begin{align}
\frac{\vec J(\vec r', t_r)}{R} 
&\approx \frac{1}{r}\left[\vec J + \frac{1}{c}r'\dot J \cos \alpha\right] +\frac{r'}{r^2}\vec J \cos \alpha -  \frac{1}{c}\frac{(r')^2}{r^2}\dot J\left[\frac{1}{2} - \cos^2 \alpha \right] \\
&\approx \frac{1}{r}\left[\vec J + \frac{1}{c}r'\dot J \cos \alpha\right] \\
\end{align}
$$
Thus
$$
\begin{align}
\vec A (\vec r, t) &= \frac{\mu_0}{4\pi r} \int_{\mathbb R}\vec J + \frac{1}{c}r'\dot J \cos \alpha dr' \\
&= \frac{\mu_0}{4\pi r} 
\end{align}
$$
<% tp.file.cursor(2) %>


