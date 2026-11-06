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
We can then simplify $\frac{\rho(\vec r', t_r)}{R}$ by throwing out terms of $r$ with powers smaller than $-2$ to get:
$$
\begin{align}
\frac{\rho(\vec r', t_r)}{R} &\approx \left[\frac{1}{r} - \frac{1}{2r}\left(\frac{r'}{r}\right)^2 - \frac{r'}{r^2}\cos \alpha\right]\left[\rho(\vec r', t_c) + \frac{\dot \rho(\vec r', t_c)}{2c}\left(r'\cos \alpha - \frac{(r')^2}{2r}\right)\right] \\
&\approx \frac{\rho}{r} + \frac{\dot \rho}{2cr}\left(r' \cos \alpha - \frac{(r')^2}{2r}\right) - \frac{r' \rho}{r^2} \cos \alpha  - \frac{r' \dot \rho}{2cr^2} r' \cos^2 \alpha \\
&\approx \frac{\rho}{r} + \frac{1}{2c}\frac{r'}{r}\dot \rho \cos \alpha - \frac{1}{4c}\left(\frac{r'}{r}\right)^2 \dot \rho - \frac{r' \rho}{r^2} \cos \alpha  - \frac{1}{2c}\left(\frac{r'}{r}\right)^2 \dot \rho \cos^2 \alpha \\
&\approx \frac{1}{r}\left[\rho + \frac{1}{2c}r'\dot \rho \cos \alpha\right] -\frac{r'}{r^2}\rho \cos \alpha -  \frac{1}{2c}\frac{(r')^2}{r^2}\dot \rho\left[\frac{1}{2} - \cos^2 \alpha \right] \\
\end{align}
$$
We will assert that the total charge is $0$ so the very first term vanishes and then we will also say the final terms vanish as we already have a $\dot \rho / r$ term. This leads to the following integral:
$$
\begin{align}
\varphi(\vec r, t) &\approx \frac{1}{4\pi \epsilon_0}\int_{\mathbb R^3}\frac{r'}{2cr} \dot \rho \cos \alpha - \frac{r'}{r^2} \rho \cos \alpha d^3 r'\\
&\approx \frac{1}{4\pi \epsilon_0}\int_{\mathbb R^3}\frac{\hat r \cdot \vec r'}{2cr} \dot \rho - \frac{\hat r \cdot \vec r'}{r^2} \rho d^3 r'\\
&\approx \frac{1}{4\pi \epsilon_0}\left[\frac{1}{2cr}\hat r\cdot \int_{\mathbb R^3} \dot \rho(\vec r', t_c) \vec r' d^3 r' - \frac{1}{r^2}\hat r \cdot \int_{\mathbb R^3} \vec r' \rho(\vec r', t_c) d^3 r' \right] \\ 
&\approx \frac{1}{4\pi \epsilon_0}\left[\frac{1}{2cr}\hat r\cdot \dot p(t_c) - \frac{1}{r^2}\hat r  \cdot \vec p(t_c)\right] \\ 
\end{align}
$$
The only problem is this is wrong and should instead be
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi \epsilon_0} \left[ \frac{\hat r \cdot \dot p(t_c)}{cr} + \frac{\hat r \cdot \vec p(t_c)}{r^2}\right]
\end{align}
$$
Similarly it can be shown somehow that
$$
\begin{align}
\vec A (\vec r, t) &= \frac{\mu_0}{4\pi } \frac{\dot p(t_c)}{r}
\end{align}
$$
Now we find the electric and magnetic fields:
$$
\begin{align}
\nabla \varphi &= \frac{1}{4\pi \epsilon_0} \left[\frac{1}{c}\nabla \left(\frac{1}{r}\right) \hat r \cdot \dot p(t_c) + \frac{1}{cr}\nabla (\hat r \cdot \dot p(t_c)) + \nabla \left(\frac{1}{r^2}\right)\hat r \cdot \vec p(t_c) + \frac{1}{r^2} \nabla (\hat r \cdot \vec p(t_c))\right] \\
\end{align}
$$
Noting the following:
$$
\begin{align}
\nabla \left(\frac{1}{r}\right) &= -\frac{\hat r}{r^2} \\
\nabla \left(\frac{1}{r^2}\right) &= -2 \frac{\hat r}{r^3} \\

\frac{\partial \hat r_j}{\partial x_i} &= \frac{\partial}{\partial x_i} \left(\frac{x_j}{r}\right) \\ 
&= \frac{1}{r}\frac{\partial x_j}{\partial x_i} + x_j \frac{\partial}{\partial r}\left(\frac{1}{r}\right) \frac{\partial r}{\partial x_i} \\ 
&= \frac{1}{r}\delta_{ij} + x_j \frac{-1}{r^2} \frac{x_i}{r} \\ 
&= \frac{\delta_{ij}}{r} - \frac{1}{r}\frac{x_ix_j}{r^2} \\ 
&= \frac{\delta_{ij} - \hat r_i\hat r_j}{r} \\ 

\frac{\partial }{\partial x_i} \left(\sum_j \hat r_j \dot p_j(t_c)\right) &= \sum_j \frac{\partial}{\partial x_i} \left(\hat r_j\dot p_j(t_c)\right) \\
&= \sum_j \left(\frac{\partial \hat r_j}{\partial x_i}\dot p_j(t_c) + \hat r_j \frac{\partial \dot p_j}{\partial x_i}\right) \\
&= \sum_j \left(\frac{\delta_{ij} - \hat r_i \hat r_j}{r}\dot p_j(t_c) + \hat r_j \frac{\partial \dot p_j}{\partial t_c}\frac{\partial t_c}{\partial x_i}\right) \\
&= \sum_j \left(\frac{\delta_{ij} - \hat r_i \hat r_j}{r}\dot p_j(t_c) + \hat r_j \ddot p_j(t_c)\frac{-\hat r_i}{c}\right) \\
&= \sum_j \left(\frac{\delta_{ij}}{r}\dot p_j(t_c) - \frac{\hat r_i \hat r_j}{r}\dot p_j(t_c) - \frac{\hat r_j\hat r_i}{c} \ddot p_j(t_c)\right) \\
&= \frac{\dot p_i(t_c)}{r} - \frac{\hat r_i \hat r \cdot \dot p(t_c)}{r} - \frac{\hat r_i \hat r \cdot \ddot p(t_c)}{c} \\

\nabla \left(\hat r \cdot \dot p(t_c)\right) &= \frac{\dot p(t_c)}{r} - \frac{\hat r\cdot \dot p(t_c)}{r} \hat r - \frac{\hat r \cdot \ddot p(t_c)}{c} \hat r \\
&= \frac{\dot p(t_c) - \hat r \cdot \dot p(t_c) \hat r}{r} - \frac{\hat r \cdot \ddot p(t_c)}{c} \hat r \\

\nabla \left(\hat r \cdot p(t_c)\right)&= \frac{p(t_c) - \hat r \cdot p(t_c) \hat r}{r} - \frac{\hat r \cdot \dot p(t_c)}{c} \hat r \\
\end{align}
$$
Thus we have the electric field to be:
$$
\begin{align}
4\pi \epsilon_0\nabla \varphi &= \frac{1}{c}\frac{-\hat r}{r^2} \hat r \cdot \dot p(t_c) + \frac{1}{cr}\left[\frac{\dot p(t_c) - \hat r \cdot \dot p(t_c) \hat r}{r} - \frac{\hat r \cdot \ddot p(t_c)}{c} \hat r\right]\\
&\ \ \ \  - \frac{2\hat r}{r^3}\hat r \cdot \vec p(t_c) + \frac{1}{r^2} \left[\frac{p(t_c) - \hat r \cdot p(t_c) \hat r}{r} - \frac{\hat r \cdot \dot p(t_c)}{c} \hat r\right]\\

&= - \frac{\hat r \cdot \dot p(t_c)\hat r}{cr^2} + \frac{\dot p(t_c)}{cr^2} - \frac{\hat r \cdot \dot p(t_c) \hat r}{cr^2} - \frac{\hat r \cdot \ddot p(t_c)}{c^2r} \hat r\\
&\ \ \ \  - \frac{2\hat r\cdot \vec p(t_c)\hat r}{r^3} + \frac{\vec p(t_c)}{r^3} - \frac{\hat r \cdot \vec p(t_c) \hat r}{r^3} - \frac{\hat r \cdot \dot p(t_c)}{c r^2} \hat r\\

&= - \frac{3\hat r \cdot \dot p(t_c)\hat r}{cr^2} + \frac{\dot p(t_c)}{cr^2} - \frac{\hat r \cdot \ddot p(t_c)}{c^2r} \hat r\\
&\ \ \ \  - \frac{3\hat r\cdot \vec p(t_c)\hat r}{r^3} + \frac{\vec p(t_c)}{r^3} \\

&= \frac{\dot p(t_c)-3\hat r \cdot \dot p(t_c)\hat r}{cr^2} + \frac{\vec p(t_c)-3\hat r\cdot \vec p(t_c)\hat r}{r^3} - \frac{\hat r \cdot \ddot p(t_c)}{c^2r} \hat r\\
\end{align}
$$
<% tp.file.cursor(2) %>