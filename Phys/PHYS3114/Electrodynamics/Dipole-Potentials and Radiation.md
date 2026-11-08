## Calculating $\vec E, \vec B$ of a dipole
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
&\approx \frac{1}{r} - \frac{1}{2r}\left(\frac{r'}{r}\right)^2 + \frac{r'}{r^2}\cos \alpha\\

\rho(\vec r', t_r) &= \rho(\vec r', t - r / c) + \dot \rho(\vec r', t - r / c)(t_r - t + r / c) + \dots\\
&\approx \rho(\vec r', t - r / c) + \dot \rho(\vec r', t - r / c)(-R / c + r / c) \\
&\approx \rho(\vec r', t - r / c) + \frac{\dot \rho(\vec r', t - r / c)}{c}\left(r - r - \frac{(r')^2}{2r} + r'\cos \alpha\right) \\
&\approx \rho(\vec r', t - r / c) + \frac{\dot \rho(\vec r', t - r / c)}{c}\left(r'\cos \alpha - \frac{(r')^2}{2r} \right) \\
\end{align}
$$
We can then simplify $\frac{\rho(\vec r', t_r)}{R}$ by throwing out terms of $r$ with powers smaller than $-2$ to get:
$$
\begin{align}
\frac{\rho(\vec r', t_r)}{R} &\approx \left[\frac{1}{r} - \frac{1}{2r}\left(\frac{r'}{r}\right)^2 + \frac{r'}{r^2}\cos \alpha\right]\left[\rho(\vec r', t_c) + \frac{\dot \rho(\vec r', t_c)}{c}\left(r'\cos \alpha - \frac{(r')^2}{2r}\right)\right] \\
&\approx \frac{\rho}{r} + \frac{\dot \rho}{cr}\left(r' \cos \alpha - \frac{(r')^2}{2r}\right) + \frac{r' \rho}{r^2} \cos \alpha  - \frac{r' \dot \rho}{cr^2} r' \cos^2 \alpha \\
&\approx \frac{\rho}{r} + \frac{1}{c}\frac{r'}{r}\dot \rho \cos \alpha - \frac{1}{2c}\left(\frac{r'}{r}\right)^2 \dot \rho + \frac{r' \rho}{r^2} \cos \alpha  - \frac{1}{c}\left(\frac{r'}{r}\right)^2 \dot \rho \cos^2 \alpha \\
&\approx \frac{1}{r}\left[\rho + \frac{1}{c}r'\dot \rho \cos \alpha\right] +\frac{r'}{r^2}\rho \cos \alpha -  \frac{1}{c}\frac{(r')^2}{r^2}\dot \rho\left[\frac{1}{2} - \cos^2 \alpha \right] \\
\end{align}
$$
We will assert that the total charge is $0$ so the very first term vanishes and then we will also say the final terms vanish as we already have a $\dot \rho / r$ term. This leads to the following integral:
$$
\begin{align}
\varphi(\vec r, t) &\approx \frac{1}{4\pi \epsilon_0}\int_{\mathbb R^3}\frac{r'}{cr} \dot \rho \cos \alpha + \frac{r'}{r^2} \rho \cos \alpha d^3 r'\\
&\approx \frac{1}{4\pi \epsilon_0}\int_{\mathbb R^3}\frac{\hat r \cdot \vec r'}{cr} \dot \rho + \frac{\hat r \cdot \vec r'}{r^2} \rho d^3 r'\\
&\approx \frac{1}{4\pi \epsilon_0}\left[\frac{1}{cr}\hat r\cdot \int_{\mathbb R^3} \dot \rho(\vec r', t_c) \vec r' d^3 r' + \frac{1}{r^2}\hat r \cdot \int_{\mathbb R^3} \vec r' \rho(\vec r', t_c) d^3 r' \right] \\ 
&\approx \frac{1}{4\pi \epsilon_0}\left[\frac{1}{cr}\hat r\cdot \dot p(t_c) + \frac{1}{r^2}\hat r  \cdot \vec p(t_c)\right] \\ 
\end{align}
$$
Thus we will set $\varphi$ to:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi \epsilon_0} \left[ \frac{\hat r \cdot \dot p(t_c)}{cr} + \frac{\hat r \cdot \vec p(t_c)}{r^2}\right]
\end{align}
$$
Similarly it can be shown through a lot more pain that
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
Thus we have $-\nabla \varphi$ to be:
$$
\begin{align}
4\pi \epsilon_0\nabla \varphi &= \frac{1}{c}\frac{-\hat r}{r^2} \hat r \cdot \dot p(t_c) + \frac{1}{cr}\left[\frac{\dot p(t_c) - \hat r \cdot \dot p(t_c) \hat r}{r} - \frac{\hat r \cdot \ddot p(t_c)}{c} \hat r\right]\\
&\ \ \ \  - \frac{2\hat r}{r^3}\hat r \cdot \vec p(t_c) + \frac{1}{r^2} \left[\frac{p(t_c) - \hat r \cdot p(t_c) \hat r}{r} - \frac{\hat r \cdot \dot p(t_c)}{c} \hat r\right]\\

&= - \frac{\hat r \cdot \dot p(t_c)\hat r}{cr^2} + \frac{\dot p(t_c)}{cr^2} - \frac{\hat r \cdot \dot p(t_c) \hat r}{cr^2} - \frac{\hat r \cdot \ddot p(t_c)}{c^2r} \hat r\\
&\ \ \ \  - \frac{2\hat r\cdot \vec p(t_c)\hat r}{r^3} + \frac{\vec p(t_c)}{r^3} - \frac{\hat r \cdot \vec p(t_c) \hat r}{r^3} - \frac{\hat r \cdot \dot p(t_c)}{c r^2} \hat r\\

&= - \frac{3\hat r \cdot \dot p(t_c)\hat r}{cr^2} + \frac{\dot p(t_c)}{cr^2} - \frac{\hat r \cdot \ddot p(t_c)}{c^2r} \hat r\\
&\ \ \ \  - \frac{3\hat r\cdot \vec p(t_c)\hat r}{r^3} + \frac{\vec p(t_c)}{r^3} \\

&= \frac{\dot p(t_c)-3\hat r \cdot \dot p(t_c)\hat r}{cr^2} + \frac{\vec p(t_c)-3\hat r\cdot \vec p(t_c)\hat r}{r^3} - \frac{\hat r \cdot \ddot p(t_c)}{c^2r} \hat r\\

-\nabla \varphi &= \frac{1}{4\pi \epsilon_0}\left[\frac{3\hat r \cdot \dot p(t_c)\hat r - \dot p(t_c)}{cr^2} + \frac{3\hat r\cdot \vec p(t_c)\hat r - \vec p(t_c)}{r^3} + \frac{\hat r \cdot \ddot p(t_c)}{c^2r} \hat r\right]\\
\end{align}
$$
We also need to take $\frac{\partial \vec A}{\partial t}$ which is much easier and is given by:
$$
\begin{align}
\frac{\partial \vec A}{\partial t} &= \frac{\partial}{\partial t} \left(\frac{\mu_0}{4\pi } \frac{\dot p(t_c)}{r}\right) \\
&= \frac{\mu_0}{4\pi} \frac{\ddot p(t_c)}{r} \frac{\partial t_c}{\partial t} \\
&= \frac{\mu_0}{4\pi} \frac{\ddot p(t_c)}{r} (1) \\
-\frac{\partial \vec A}{\partial t}&= -\frac{1}{4\pi\epsilon_0 c^2} \frac{\ddot p(t_c)}{r} \\
\end{align}
$$
Putting all of this together we finally get $\vec E$:
$$
\begin{align}
\vec E &= \frac{1}{4\pi \epsilon_0} \left[\frac{3 \hat r \cdot \dot p(t_c) \hat r - \dot p(t_c)}{cr^2} + \frac{3\hat r\cdot \vec p(t_c) \hat r - \vec p(t_c)}{r^3} + \frac{\hat r \cdot \ddot p (t_c) \hat r - \ddot p (t_c)}{c^2r}\right]
\end{align}
$$
Also notice that $\hat r \times (\hat r \times \ddot p) = (\hat r \cdot \ddot p) \hat r - (\hat r \cdot \hat r)\ddot p = (\hat r \cdot \ddot p) \hat r - \ddot p$ and thus the final term can be simplified to:
$$
\begin{align}
\vec E &= \frac{1}{4\pi \epsilon_0} \left[\frac{3 \hat r \cdot \dot p(t_c) \hat r - \dot p(t_c)}{cr^2} + \frac{3\hat r\cdot \vec p(t_c) \hat r - \vec p(t_c)}{r^3} + \frac{\hat r \times (\hat r \times \ddot p(t_c))}{c^2r}\right]
\end{align}
$$
We can then also do $\vec B = \nabla \times \vec A$ to end up with:
$$
\begin{align}
\vec B &= \frac{\mu_0}{4\pi} \left[\frac{\dot p \times \hat r}{r^2} + \frac{\ddot p\times \hat r}{cr}\right]
\end{align}
$$
## Radiation
As we get increasingly far away from the source the only term that matters is the $1 / r$ term. This term retains a constant energy over spherical shells around the source and thus carries all the energy away. We call this radiation.

For our dipole these are:
$$
\begin{align}
\vec E_{\text{rad}} &= \frac{1}{4\pi \epsilon_0} \frac{\hat r \times (\hat r \times \ddot p(t_c))}{c^2 r} \\
\vec B_{\text{rad}} &=  \frac{\mu_0}{4\pi} \frac{\ddot p \times \hat r}{cr}\\
\end{align}
$$
We can also notice that 
$$
\begin{align}
\hat r \times [\hat r \times (\hat r \times \ddot p(t_c))] &= \hat r \times [\hat r(\hat r \cdot \ddot p) - (\hat r \cdot \hat r) \ddot p]\\
&= (\hat r \times \hat r) (\hat r \cdot \ddot p) - (\hat r \times \ddot p) \\
&= \ddot p \times \hat r \\
\end{align}
$$
Thus we have:
$$
\begin{align}
\vec B_{\text{rad}} &= \frac{1}{c}\hat r \times \vec E_{\text{rad}}
\end{align}
$$
Further, we can calculate the energy flux to be:
$$
\begin{align}
\vec S_{\text{rad}} &= \frac{1}{\mu_0} \vec E_{\text{rad}} \times \vec B_{\text{rad}} \\
&= \frac{1}{\mu_0 c} \vec E_\text{rad} \times \left(\hat r \times \vec E_\text{rad}\right) \\
&= \frac{1}{\mu_0 c} \left[\hat r \left(\vec E_\text{rad}\cdot \vec E_\text{rad}\right) - \vec E_\text{rad} \left(\hat r \cdot  \vec E_\text{rad} \right) \right]\\ 
&= \frac{1}{\mu_0 c} \left[\hat r E_\text{rad}^2 - \vec E_\text{rad} \left(0 \right) \right]\\ 
&= \frac{E_\text{rad}^2}{\mu_0 c} \hat r  = \epsilon_0 c E_\text{rad}^2 \hat r\\ 
\end{align}
$$
Inspecting $E_\text{rad}^2$ we get:
$$
\begin{align}
E_\text{rad}^2 &= \left|\frac{1}{4\pi \epsilon_0} \frac{\hat r \times (\hat r \times \ddot p(t_c))}{c^2 r} \right|^2 \\
&= \frac{1}{16\pi^2 \epsilon_0^2c^4r^2} \left|\hat r \times (\hat r \times \ddot p(t_c)) \right|^2 \\
&= \frac{1}{16\pi^2 \epsilon_0^2c^4r^2} \left|(\hat r \cdot \ddot p)\hat r - (\hat r \cdot \hat r) \ddot p \right|^2 \\
&= \frac{1}{16\pi^2 \epsilon_0^2c^4r^2} \left|(\hat r \cdot \ddot p)\hat r -\ddot p \right|^2 \\

&= \frac{1}{16\pi^2 \epsilon_0^2c^4r^2} \left[|(\hat r \cdot \ddot p)\hat r|^2 - 2\left[(\hat r \cdot \ddot p)\hat r \cdot \ddot p\right] + |\ddot p|^2 \right] \\
&= \frac{1}{16\pi^2 \epsilon_0^2c^4r^2} \left[(\hat r \cdot \ddot p)^2 - 2(\hat r \cdot \ddot p)(\hat r \cdot \ddot p) + |\ddot p|^2 \right] \\
&= \frac{1}{16\pi^2 \epsilon_0^2c^4r^2} \left[|\ddot p|^2 - (\hat r \cdot \ddot p)^2  \right] \\
&= \frac{1}{16\pi^2 \epsilon_0^2c^4r^2} \left[|\ddot p|^2 - |\ddot p|^2 \cos^2 \theta \right] \\
&= \frac{1}{16\pi^2 \epsilon_0^2c^4r^2} |\ddot p|^2 \sin^2 \theta \\
\end{align}
$$
and thus our energy flux is:
$$
\begin{align}
\vec S_\text{rad} &= \frac{\epsilon_0 c |\ddot p|^2\sin^2\theta}{16\pi^2 \epsilon_0^2 c^4 r^2} \hat r\\
&= \frac{|\ddot p(t_r)|^2\sin^2\theta}{16 \pi^2 \epsilon_0c^3 r^2} \hat r
\end{align}
$$
Finally, we can integrate this over a sphere of radius $R$ for the total power lost:
$$
\begin{align}
\mathcal P &= \oint_S \frac{|\ddot p(t_r)|^2\sin^2\theta}{16 \pi^2 \epsilon_0c^3 r^2} \hat r \cdot d\Omega \\
&= \frac{|\ddot p(t_r)|^2}{16 \pi^2 \epsilon_0c^3R^2}\int_0^{2\pi}\int_0^\pi \sin^2\theta R^2\sin \theta d\theta d\phi \\
&= \frac{|\ddot p(t_r)|^2}{16 \pi^2 \epsilon_0c^3}\int_0^{2\pi}d\phi\int_0^\pi \sin^3\theta d\theta \\
&= \frac{|\ddot p(t_r)|^2}{8 \pi \epsilon_0c^3}\frac{4}{3} \\
&= \frac{|\ddot p(t_r)|^2}{6 \pi \epsilon_0c^3} \\
\end{align}
$$
<% tp.file.cursor(2) %>