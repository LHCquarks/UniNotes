The Multi-pole expansion in electrodynamics is more involved however it gets us to some powerful formulas for radiation. This is a long derivation and so deserves an outline of the proof. We will:
1. Taylor expand $R = |\vec r - \vec r'|$
2. Taylor expand $\rho(\vec r, t_r)$ and $\vec J (\vec r, t_r)$ in $t$ around $t_c = t - r/c$ using 1.
3. Taylor expand $1/R$
4. Use 2. and 3. to find the expansions of $\rho  / R$ and $\vec J / R$ 
5. Substitute in 4. to the formulas for $\varphi$ and $\vec A$ respectively to find them
6. Find the $\vec E$ and $\vec B$ radiation from the potential functions
7. Observe that for the $1/r$ terms $\vec B = \frac{1}{c} \hat n \times \vec E$ 
8. Get an expression for the Poynting vector
9. Find the total power radiated from our source
Because we are interested in only the far field of our sources (the radiation) we are going throw away any terms for $\vec E$ and $\vec B$ that fall away faster than $1/r$. Due to all these steps never introducing any $r$ terms when we see a term that is $\mathcal O(1/r^2)$ we will disregard it and throw it away.
With all that preamble lets start the derivation.
## Taylor expanding $R$
We start by using the cosine law to express $R$ as
$$
\begin{align}
R &= \sqrt{r^2 + (r')^2 - 2rr'\cos \alpha} \\
&= r \sqrt{1 + \left(\frac{r'}{r}\right)^2 - 2\left(\frac{r'}{r}\right)\cos \alpha}
\end{align}
$$
We can then use the Taylor expansion for $(1 + x)^{1/2} = 1 + \frac{1}{2}x - \frac{1}{8}x^2 + \mathcal O(x^3)$ and the fact that $\mathcal O(x) = \mathcal O(r'/r)$ to get:
$$
\begin{align}
R &= r\left[1 + 
\frac{1}{2}\left(\left(\frac{r'}{r}\right)^2 - 2\left(\frac{r'}{r}\right)\cos \alpha\right) - 
\frac{1}{8}\left(\left(\frac{r'}{r}\right)^2 - 2\left(\frac{r'}{r}\right)\cos\alpha\right)^2\right] \\

&= r + 
\frac{(r')^2}{2r} - r'\cos \alpha - 
\frac{r}{8}\left(\left(\frac{r'}{r}\right)^4  - 4\left(\frac{r'}{r}\right)^3 +  4\left(\frac{r'}{r}\right)^2\cos^2\alpha\right) \\

&= r + 
\frac{(r')^2}{2r} - r'\cos \alpha - 
\frac{(r')^4}{8r^3}  + \frac{(r')^3}{2r^2} -  \frac{(r')^2}{2r}\cos^2\alpha \\

&= r + 
\frac{(r')^2}{2r} - r'\cos \alpha -  
\frac{(r')^2}{2r}\cos^2\alpha \\

&= r + \frac{(r')^2}{2r}\sin^2\alpha - r'\cos \alpha \\
\end{align}
$$
Wonderful, we will store this for when we expand $\rho$ and $\vec J$.
## Expanding $\rho$ and $\vec J$
Start with $\rho(\vec r, t)$ we can Taylor expand this in $t$ around $t_c$ then substitute in $t = t_r$ to get
$$
\begin{align}
\rho(\vec r, t) &= \rho(\vec r, t_c) + \dot \rho(\vec r, t_c) (t - t_c) + \frac{1}{2} \ddot \rho(\vec r, t_c) (t - t_c)^2 + \mathcal O((t - t_c)^3) \\
\rho(\vec r, t_r) &= \rho(\vec r, t_c) + \dot \rho(\vec r, t_c) (t_r - t_c) + \frac{1}{2} \ddot \rho(\vec r, t_c) (t_r - t_c)^2 + \mathcal O((t_r - t_c)^3) \\
\end{align}
$$
Further, using part 1 we get:
$$
\begin{align}
t_r - t_c &= t - R/c - t + r/c \\
&= \frac{1}{c}\left[r - R\right] \\
&= \frac{1}{c}\left[r - r + \frac{(r')^2}{2r}\sin^2\alpha - r'\cos \alpha\right] \\
&= \frac{(r')^2}{2cr}\sin^2\alpha - \frac{r'}{c}\cos \alpha \\
\end{align}
$$
We also argue that as $\lambda << r$ we will have that $(\frac{r - R}{c})^2$ vanishes thus our Taylor expansion becomes:
$$
\begin{align}
\rho(\vec r, t_r) &= \rho(\vec r, t_c) + \dot \rho(\vec r, t_c) \left(\frac{(r')^2}{2cr}\sin^2\alpha - \frac{r'}{c}\cos\alpha \right) \\
\rho(\vec r, t_r) &= \rho(\vec r, t_c) + \dot \rho(\vec r, t_c) \frac{(r')^2}{2cr}\sin^2\alpha - \dot\rho(\vec r, t_c)\frac{r'}{c}\cos\alpha \\
\end{align}
$$
Similarly we can apply the exact same arguments to each component of $\vec J$ and then sum them all back up to get
$$
\begin{align}
\vec J (\vec r, t_r) &= \vec J(\vec r, t_c) + \dot J(\vec r, t_c) \frac{(r')^2}{2cr} \sin^2 \alpha - \dot J(\vec r, t_c) \frac{r'}{c}\cos \alpha
\end{align}
$$
Wonderful.
## Finding $1/R$
This will almost be identical to finding $R$. Start with $1/R$, use the cosine law and apply the Taylor series $(1 + x)^{-1/2} = 1 - \frac{1}{2}x + \mathcal O(x^2)$.
$$
\begin{align}
\frac{1}{R} &= [r^2 + (r')^2 - 2rr'\cos\alpha]^{-1/2} \\
\frac{1}{R} &= \frac{1}{r}\left[1 + \left(\frac{r'}{r}\right)^2 - 2\left(\frac{r'}{r}\right)\cos\alpha\right]^{-1/2} \\
\frac{1}{R} &= \frac{1}{r}\left[1 -\frac{1}{2}\left(\left(\frac{r'}{r}\right)^2 -2\left(\frac{r'}{r}\right)\cos\alpha\right) \right] \\
\frac{1}{R} &= \frac{1}{r} - \frac{(r')^2}{2r^3} + \frac{r'}{r^2}\cos\alpha\\
\frac{1}{R} &= \frac{1}{r} \\
\end{align}
$$
Great. With this we can finally put it all together to get $\varphi, \vec A$!
## Finding $\varphi$ and $\vec A$
First we will start with $\varphi$ but before we can find $\varphi$ we need to find $\frac{\rho(\vec r', t_r)}{R}$ using our prior expansions like so:
$$
\begin{align}
\frac{\rho(\vec r', t_r)}{R} &= \left[\rho(\vec r, t_c) + \dot \rho(\vec r, t_c) \frac{(r')^2}{2cr}\sin^2\alpha - \dot\rho(\vec r, t_c)\frac{r'}{c}\cos\alpha\right] \cdot \left[\frac{1}{r}\right] \\
&= \frac{\rho(\vec r, t_c)}{r} + \frac{\dot \rho(\vec r, t_c)\sin^2\alpha}{2c}\left(\frac{r'}{r}\right)^2 - \frac{\dot \rho(\vec r, t_c)r'\cos \alpha}{cr} \\
&= \frac{\rho(\vec r, t_c)}{r} - \frac{\dot \rho(\vec r, t_c)r'\cos \alpha}{cr} \\
\end{align}
$$
Ok, now we have this we can solve for $\varphi$ like so:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0}\int_{\mathbb R^3} \frac{\rho(\vec r', t_r)}{R} d^3r' \\
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0}\int_{\mathbb R^3} \frac{\rho(\vec r', t_c)}{r} - \frac{\dot \rho(\vec r', t_c) r' \cos\alpha}{cr} d^3r' \\
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0r}\int_{\mathbb R^3} \rho(\vec r', t_c) d^3r' - \frac{1}{4\pi\epsilon_0cr}\int_{\mathbb R^3}\dot \rho(\vec r', t_c) r' \cos\alpha d^3r' \\
\varphi(\vec r, t) &= \frac{Q}{4\pi\epsilon_0r} - \frac{\dot p(t_c) \cdot \hat n}{4\pi\epsilon_0cr}\\
\end{align}
$$
Very cool.

Doing a similar thing with $\vec A$ yeilds:
$$
\begin{align}
\frac{\vec J(\vec r', t_r)}{R} &= \frac{\vec J(\vec r', t_c)}{r} - \frac{\dot J(\vec r', t_c)r'\cos \alpha}{cr} \\
\vec A &= \frac{\mu_0}{4\pi} \int_{\mathbb R^3} \frac{\vec J(\vec r', t_c)}{r} - \frac{\dot J(\vec r', t_c)r'\cos \alpha}{cr} d^3 r'\\
&= \frac{\mu_0}{4\pi r} \int_{\mathbb R^3} \vec J(\vec r', t_c)d^3 r' - \frac{\mu_0}{4\pi cr} \int_{\mathbb R^3} \dot J(\vec r', t_c) r'\cos \alpha d^3 r' \\
\end{align}
$$
For the first term we will apply a vectorial by parts like so:
$$
\begin{align}
\nabla\cdot (r'_i \vec J) &=  \nabla r'_i \cdot \vec J + r'_i \nabla \cdot \vec J \\
\nabla\cdot (r'_i \vec J) &=  \hat e_i \cdot \vec J - r'_i \dot \rho \\
\int_{\mathbb R^3}\nabla\cdot (r'_i \vec J)d^3r' &=  \int_{\mathbb R^3} J_i d^3r'- \int_{\mathbb R^3}r'_i \dot \rho d^3r'\\
\int_{S} r'_i \vec J \cdot d\vec S &=  \int_{\mathbb R^3} J_i d^3r'- \int_{\mathbb R^3}r'_i \dot\rho d^3r'\\
\end{align}
$$
But assuming that $\vec J$ vanishes far before $r$ we have the left hand term to be $0$. Further, we can then replace the component terms ($J_i, r'_i$) with their vectorial counterparts to find
$$
\begin{align}
\int_{\mathbb R^3} \vec J (\vec r', t_c)d^3r' &= \int_{\mathbb R^3} \dot\rho \vec r' d^3 r' \\
&= \dot p(t_c)
\end{align}
$$
Great, now substituting this back in we have 
