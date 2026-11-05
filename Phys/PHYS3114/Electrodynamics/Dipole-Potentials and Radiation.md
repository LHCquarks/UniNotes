Assume we have a time varying perfect electric dipole at the origin $\vec p(t)$.

We will start by finding our $\varphi$ and $\vec A$ using our Green's function:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi \epsilon_0} \int_{\mathbb R^3} \frac{\rho(\vec r', t_r)}{R} dr'
\end{align}
$$
We can now use a bunch of Taylor expansions and the cosine law to get the following approximations:
$$
\begin{align}
R &= \sqrt{r^2 + (r')^2 - 2rr'\cos\alpha} \\
&= r\left(1 + \left(\frac{r'}{r}\right)^2 - 2 \left(\frac{r'}{r}\right)\cos \alpha\right)^{1/2} \\
&= r (1 + \epsilon)^{1/2} \\
&= r \left[1 + \frac{1}{2}\epsilon + \dots \right] \\
&\approx r \left[1 + \frac{1}{2}\left(\frac{r'}{r}\right)^2 - \frac{r'}{r} \cos \alpha \right] \\
&\approx r + \frac{(r')^2}{2r} - r' \cos \alpha \\
\frac{1}{R} &= \frac{1}{r}(1 + \epsilon)^{- 1/2}\\
&= \frac{1}{r}\left[1 - \frac{1}{2}\epsilon + \dots\right]\\
&\approx \frac{1}{r} - \frac{1}{2r}\left(\frac{r'}{r}\right)^2 - \frac{r'}{r^2}\cos \alpha\\
\rho(\vec r', t_r) &= \rho(\vec r', t - r / c) + \frac{\dot \rho(\vec r', t - r / c)}{2}(t_r - t + r / c) + \dots\\
&\approx \rho(\vec r', t - r / c) + \frac{\dot \rho(\vec r', t - r / c)}{2}(-R / c + r / c) \\
&\approx \rho(\vec r', t - r / c) + \frac{\dot \rho(\vec r', t - r / c)}{2c}\left(r - r - \frac{(r')^2}{2r} + r'\cos \alpha\right) \\
&\approx \rho(\vec r', t - r / c) + \frac{\dot \rho(\vec r', t - r / c)}{2c}\left(r'\cos \alpha - \frac{(r')^2}{2r} \right) \\
\end{align}
$$
We can then simplify $\frac{\rho(\vec r', t_r)}{R}$ to be:
$$
\begin{align}
\frac{\rho(\vec r', t_r)}{R} &\approx \left[\frac{1}{r} - \frac{1}{2r}\left(\frac{r'}{r}\right)^2 - \frac{r'}{r^2}\cos \alpha\right]\left[\rho(\vec r', t_c) + \frac{\dot \rho(\vec r', t_c)}{2c}\left(r'\cos \alpha - \frac{(r')^2}{2r}\right)\right] \\
&\approx 
\end{align}
$$
<% tp.file.cursor(2) %>

and using these our $\varphi(\vec r, t)$ goes to
$$
\begin{align}
\varphi(\vec r, t) &\approx \frac{1}{4\pi \epsilon_0} \int_{\mathbb R^3} \left[\frac{1}{r} - \frac{1}{2r}\left(\frac{r'}{r}\right)^2 - \frac{r'}{r^2}\cos \alpha\right]\left[\rho(\vec r', t_c) + \frac{\dot \rho(\vec r', t_c)}{2c}\left(r'\cos \alpha - \frac{(r')^2}{2r}\right)\right] \\
&\approx 
\end{align}
$$
Now, because we assumed this was a electric mono-pole no matter the time we have that all but the $n=1$ terms vanish leaving us with:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0} \frac{1}{r^2} \int_{\mathbb R^3} r' \cos\alpha \rho(\vec r', t_r) dr' \\
 &= \frac{1}{4\pi\epsilon_0} \frac{1}{r^2} \int_{\mathbb R^3} \hat r \cdot \vec r' \rho(\vec r', t_r) dr' \\
 &= \frac{1}{4\pi\epsilon_0} \frac{1}{r^2} \hat r \cdot\int_{\mathbb R^3}  \vec r' \rho(\vec r', t_r) dr' \\
\end{align}
$$
On top of this we can then Taylor expand $\rho(\vec r', t_r)$ in the $t'$ slot around $t_c = t - |r| / c$ like so:
$$
\begin{align}
\rho(\vec r', t_r) &= \rho(\vec r', t_c) + \frac{1}{2}\rho(\vec r', t_c) (t_r - t_c) + \dots \\
&\approx \rho(\vec r', t_c) + \frac{t - |r' - r| / c - t + |r| / c}{2} \rho(\vec r', t_c) \\
&\approx \rho(\vec r', t_c) + \frac{|r| - |r' - r|}{c} \rho(\vec r', t_c) \\

\end{align}
$$
<% tp.file.cursor(2) %>
