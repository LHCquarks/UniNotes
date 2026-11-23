The Multi-pole expansion in electrodynamics is more involved however it gets us to some powerful formulas for radiation. This is a long derivation and so deserves an outline of the proof. We will:
1. Taylor expand $R = |\vec r - \vec r'|$
2. Taylor expand $\rho(\vec r, t_r)$ and $\vec J (\vec r, t_r)$ in $t$ around $t_c = t - r/c$ using 1.
3. Taylor expand $1/R$
4. Use 2. and 3. to find the expansions of $\rho  / R$ and $\vec J / R$ 
5. Find $\varphi$ using 4.
6. Find $\vec A$ using 4.
7. Find $\vec E$ radiation from potential functions
8. Find $\vec B$ radiation from the potential functions
9. Observe that for the $1/r$ terms $\vec B = \frac{1}{c} \hat n \times \vec E$ 
10. Get an expression for the Poynting vector
11. Find the total power radiated from our source
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
&= \frac{1}{c}\left[r - r - \frac{(r')^2}{2r}\sin^2\alpha + r'\cos \alpha\right] \\
&= -\frac{(r')^2}{2cr}\sin^2\alpha + \frac{r'}{c}\cos \alpha \\
\end{align}
$$
We also argue that as $\lambda << r$ we will have that $(\frac{r - R}{c})^3$ vanishes thus our Taylor expansion becomes:
$$
\begin{align}
\rho(\vec r', t_r) &= \rho + \dot \rho \left(\frac{r'}{c}\cos\alpha - \frac{(r')^2}{2cr}\sin^2\alpha\right) + \frac{\ddot \rho}{2}\left(-\frac{(r')^2}{2cr}\sin^2\alpha + \frac{r'}{c}\cos\alpha \right)^2\\
\rho(\vec r', t_r) &= \rho + \dot\rho(\vec r, t_c)\frac{r'}{c}\cos\alpha - \dot \rho \frac{(r')^2}{2cr}\sin^2\alpha \\ 
&\ \ \ \ \ +\frac{\ddot \rho (r')^4}{8c^2r^2}\sin^4\alpha - \frac{\ddot \rho(r')^3}{2c^2 r}\sin^2\alpha \cos\alpha + \frac{\ddot \rho(r')^2}{2c^2}\cos^2 \alpha \\
\rho(\vec r', t_r) &= \rho + \dot\rho(\vec r, t_c)\frac{r'}{c}\cos\alpha - \dot \rho \frac{(r')^2}{2cr}\sin^2\alpha - \frac{\ddot \rho(r')^3}{2c^2 r}\sin^2\alpha \cos\alpha + \frac{\ddot \rho(r')^2}{2c^2}\cos^2 \alpha \\
\end{align}
$$
Similarly we can apply the exact same arguments to each component of $\vec J$ and then sum them all back up to get
$$
\begin{align}
\vec J (\vec r, t_r) &= \vec J(\vec r, t_c) + \dot J(\vec r, t_c) \frac{r'}{c}\cos \alpha - \dot J(\vec r, t_c) \frac{(r')^2}{2cr} \sin^2 \alpha
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
## Finding $\varphi$
First we will start with $\varphi$ but before we can find $\varphi$ we need to find $\frac{\rho(\vec r', t_r)}{R}$ using our prior expansions like so:
$$
\begin{align}
\frac{\rho(\vec r', t_r)}{R} &= \frac{1}{r}\left[\rho(\vec r, t_c) - \dot \rho(\vec r, t_c) \frac{(r')^2}{2cr}\sin^2\alpha + \dot\rho(\vec r, t_c)\frac{r'}{c}\cos\alpha \\ - \frac{\ddot \rho(r')^3}{2c^2 r}\sin^2\alpha \cos\alpha + \frac{\ddot \rho(r')^2}{2c^2}\cos^2 \alpha  \right] \\
&= \frac{\rho(\vec r, t_c)}{r} - \frac{\dot \rho(\vec r, t_c)\sin^2\alpha}{2c}\left(\frac{r'}{r}\right)^2 + \frac{\dot \rho(\vec r, t_c)r'\cos \alpha}{cr} \\ 
&\ \ \ \ \ - \frac{\ddot \rho(r')^3}{2c^2 r^2}\sin^2\alpha \cos\alpha + \frac{\ddot \rho(r')^2}{2c^2r}\cos^2 \alpha \\
&= \frac{\rho(\vec r, t_c)}{r} + \frac{\dot \rho(\vec r, t_c)r'\cos \alpha}{cr} + \frac{\ddot \rho(r')^2}{2c^2r}\cos^2 \alpha\\
\end{align}
$$
Ok, now we have this we can solve for $\varphi$ like so:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0}\int_{\mathbb R^3} \frac{\rho(\vec r', t_r)}{R} d^3r' \\
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0}\int_{\mathbb R^3} \frac{\rho(\vec r', t_c)}{r} + \frac{\dot \rho(\vec r', t_c) r' \cos\alpha}{cr} + \frac{\ddot \rho(\vec r', t_c)(r')^2}{2c^2r}\cos^2 \alpha d^3r' \\
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0r}\int_{\mathbb R^3} \rho(\vec r', t_c) d^3r' + \frac{1}{4\pi\epsilon_0cr}\int_{\mathbb R^3}\dot \rho(\vec r', t_c) r' \cos\alpha d^3r' \\
&\ \ \ \ \  + \frac{1}{8\pi\epsilon_0 c^2 r}\int_{\mathbb R^3} \ddot \rho(\vec r', t_c) (r'^2) \cos^2 \alpha d^3r'\\
\varphi(\vec r, t) &= \frac{Q}{4\pi\epsilon_0r} + \frac{\dot p(t_c) \cdot \hat n}{4\pi\epsilon_0cr} + \frac{1}{8\pi\epsilon_0c^2r}\int_{\mathbb R^3} \ddot \rho (\vec r' \cdot \hat n)^2 d^3 r'   \\ 
\end{align}
$$
Very cool.
### Tensor Algebra aside
We will now try to simplify the third term of our scalar potential using a new object we will define.

Define the electric quadrapole tensor as:
$$
\begin{align}
M_{ij}(t) &= \int_{\mathbb R^3} \rho(\vec r' , t) r_i' r_j' d^3r' \\
\end{align}
$$
Our integral has the form:
$$
\begin{align}
\int_{\mathbb R^3} \ddot \rho(\vec r', t_c)  (r_i'n_i)^2 d^3 r' &= \int_{\mathbb R^3} \ddot \rho(\vec r', t_c) (r_i'n_i)(r_j'n_j) d^3 r' \\
&= n_in_j\int_{\mathbb R^3} \ddot \rho(\vec r', t_c)r_i'r_j'd^3r'\\
&= n_in_j\ddot M_{ij} \\
&= \hat n \cdot \ddot M \cdot \hat n
\end{align}
$$
This leaves us with a scalar potential of:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{Q}{4\pi\epsilon_0 r} + \frac{\dot p(t_c) \cdot \hat n}{4\pi c\epsilon_0 r} + \frac{\hat n \cdot M \cdot \hat n}{8\pi\epsilon_0c^2r}
\end{align}
$$

## Finding $\vec A$
Doing a similar thing with $\vec A$ yields:
$$
\begin{align}
\frac{\vec J(\vec r', t_r)}{R} &= \frac{\vec J(\vec r', t_c)}{r} + \frac{\dot J(\vec r', t_c)r'\cos \alpha}{cr} \\
\vec A &= \frac{\mu_0}{4\pi} \int_{\mathbb R^3} \frac{\vec J(\vec r', t_c)}{r} + \frac{\dot J(\vec r', t_c)r'\cos \alpha}{cr} d^3 r'\\
&= \frac{\mu_0}{4\pi r} \int_{\mathbb R^3} \vec J(\vec r', t_c)d^3 r' + \frac{\mu_0}{4\pi cr} \int_{\mathbb R^3} \dot J(\vec r', t_c) r'\cos \alpha d^3 r' \\
\end{align}
$$
These terms (especially the second) are not trivially solved so we will investigate them seperatly starting with the first.
### First term
For the first term we will inspect it by component and use an integration by parts
$$
\begin{align}
\nabla\cdot (r'_i \vec J) &=  \nabla r'_i \cdot \vec J + r'_i \nabla \cdot \vec J \\
\nabla\cdot (r'_i \vec J) &=  \hat e_i \cdot \vec J - r'_i \dot \rho \\
\int_{\mathbb R^3}\nabla\cdot (r'_i \vec J)d^3r' &=  \int_{\mathbb R^3} J_i d^3r'- \int_{\mathbb R^3}r'_i \dot \rho d^3r'\\
\oint_{S} r'_i \vec J \cdot d\vec S &=  \int_{\mathbb R^3} J_i d^3r'- \int_{\mathbb R^3}r'_i \dot\rho d^3r'\\
\end{align}
$$
But assuming that $\vec J$ vanishes far before $r$ we have the left hand term to be $0$. Further, we can then replace the component terms ($J_i, r'_i$) with their vectorial counterparts to find
$$
\begin{align}
\int_{\mathbb R^3} \vec J (\vec r', t_c)d^3r' &= \int_{\mathbb R^3} \dot\rho \vec r' d^3 r' \\
&= \dot p(t_c)
\end{align}
$$
### Second term
Using $\vec r' \cdot \hat n = r'\cos \alpha$ we get:
$$
\begin{align}
\int_{\mathbb R^3} \dot J(\vec r', t_c) r' \cos \alpha d^3 r' &= \int_{\mathbb R^3} \dot J(\vec r', t_c) (\vec r' \cdot \hat n) d^3r'
\end{align}
$$
We will now look at this in component form. Define the tensor
$$
\begin{align}
I_{ij}(t) &= \int_{\mathbb R^3} r_i'J_j(\vec r', t) d^3r' \\
\end{align}
$$
Then our integral is just
$$
\begin{align}
\left(\int_{\mathbb R^3} \dot J(\vec r', t_c) (\vec r' \cdot \hat n) d^3r'\right)_j &= \sum_{i}\hat n_i\dot I_{ij}(t_c)
\end{align}
$$
Sick. Now lets investigate this $I_{ij}$ object
#### Another tensor algebra detour
To make sense of $I_{ij}$ we will decompose it into it's antisymetric and symmetric parts like so:
$$
\begin{align}
I_{ij} &= \frac{1}{2}(I_{ij} + I_{ji}) + \frac{1}{2}(I_{ij} - I_{ji})
\end{align}
$$
As a reminder we define the electric quadrapole tensor as:
$$
\begin{align}
M_{ij}(t) &= \int_{\mathbb R^3} \rho(\vec r' , t) r_i' r_j' d^3r' \\
\dot M_{ij}(t) &= \int_{\mathbb R^3} \dot \rho(\vec r' , t) r_i' r_j' d^3r' \\
\end{align}
$$
by the continuity equation $\dot \rho = - \nabla \cdot \vec J = -\partial_k \vec J_k$ where $k$ is summed over and thus:
$$
\begin{align}
\dot M_{ij}(t) &= -\int_{\mathbb R^3} \partial_k(J_k) r_i'r_j'd^3r' \\
&= -\oint J_k r_i'r_j' d\Omega + \int_{\mathbb R^3} J_k \partial_k(r_i'r_j') d^3r'
\end{align}
$$
but the surface term vanishes as $J_k$ vanishes leaving just the second term which gives:
$$
\begin{align}
\dot M_{ij}(t) &= \int_{\mathbb R^3} J_k [\delta_{ik}r_j' + r_i'\delta_{jk}] d^3r' \\
&= \int_{\mathbb R^3} J_k \delta_{ik}r_j' d^3r' + \int_{\mathbb R^3} J_k r_i'\delta_{jk}d^3r' \\
&= \int_{\mathbb R^3} J_i r_j' d^3r' + \int_{\mathbb R^3} J_j r_i'd^3r' \\
&= I_{ij} + I_{ji} \\
\end{align}
$$
Thus this $\dot M_{ij}(t)$ is the symmetric part of $I_{ij}$.
For the anti-symmetric case lets inspect the magnetic dipole moment:
$$
\begin{align}
m(t) &= \frac{1}{2} \int_{\mathbb R^3}  \vec r' \times \vec J(\vec r', t) d^3r' \\
\end{align}
$$
Using the Levi-Civita symbol $\epsilon_{ijk}$ we can simplify this cross product to:
$$
\begin{align}
m_k(t) &= \frac{1}{2}\int_{\mathbb R^3} \epsilon_{klm} r_l'J_m d^3r' \\
m_k(t) &= \frac{\epsilon_{klm}}{2}\int_{\mathbb R^3} r_l'J_m d^3r' \\
m_k(t) &= \frac{\epsilon_{klm}}{2}I_{lm} \\
\end{align}
$$
Using the identity that $\epsilon_{ijk}\epsilon_{klm} = \delta_{il}\delta_{jm} - \delta_{im}\delta_{jl}$ we get that:
$$
\begin{align}
\epsilon_{ijk}m_k(t) &= \frac{I_{lm}}{2} [\delta_{il}\delta_{jm} - \delta_{im}\delta_{jl}] \\
&= \frac{1}{2} [I_{ij} - I_{ji}] \\
\end{align}
$$
thus the antisymetric part is just the magnetic dipole moment with this $\epsilon_{ijk}$ sign changer.
#### Finishing the second integral
With these new definitions we can find our integral to be:
$$
\begin{align}
\left(\int_{\mathbb R^3} \dot J(\vec r', t_c) (\vec r' \cdot \hat n) d^3r'\right)_j &= \sum_{i}\hat n_i\dot I_{ij}(t_c) \\
&= \hat n_i \left(\frac{\ddot M_{ij}(t_c)}{2} + \epsilon_{ijk}\dot m_k(t_c)\right) \\
\int_{\mathbb R^3} \dot J(\vec r', t_c) (\vec r' \cdot \hat n) d^3r' &= \frac{\ddot M(t_c)\hat n}{2} + \dot m(t_c) \times \hat n
\end{align}
$$
### Total integral
With this we find $\vec A$ to be:
$$
\begin{align}
\vec A &= \frac{\mu_0\dot p(t_c)}{4\pi r} + \frac{\mu_0\ddot M(t_c)\hat n}{8\pi cr} + \frac{\mu_0 \dot m(t_c) \times \hat n}{4\pi cr}\\
\end{align}
$$
## Finding $\vec E$
To do this we first need to find $\nabla \varphi$ and $\frac{\partial \vec A}{\partial t}$ first.
### Finding $\nabla \varphi$
$$
\begin{align}
\nabla \varphi &= \frac{Q}{4\pi \epsilon_0} \nabla \left(\frac{1}{r}\right) + \frac{1}{4\pi\epsilon_0 c} \nabla \left(\frac{\dot p(t_c) \cdot \hat n}{r}\right) + \frac{1}{8\pi\epsilon_0 c^2} \nabla \left(\frac{\hat n \cdot \ddot M \cdot \hat n}{r}\right)\\
&= -\frac{Q}{4\pi \epsilon_0} \frac{\hat n}{r^2} + \frac{1}{4\pi\epsilon_0 c} \nabla \left(\frac{1}{r}\right)(\dot p(t_c) \cdot \hat n) + \frac{1}{4\pi\epsilon_0 cr} \nabla \left(\dot p(t_c) \cdot \hat n\right) \\
&\ \ \ \ + \frac{1}{8\pi\epsilon_0c^2} \nabla\left(\frac{1}{r}\right)\hat n \cdot \ddot M \cdot \hat n  + \frac{1}{8\pi\epsilon_0 c^2 r}\nabla(\hat n \cdot \ddot M \cdot \hat n ) \\ 
&= - \frac{\left[\dot p(t_c) \cdot \hat n\right]\hat n}{4\pi\epsilon_0 c r^2} + \frac{1}{4\pi\epsilon_0 cr} \nabla \left(\dot p(t_c) \cdot \hat n\right) - \frac{\hat n \ddot M \hat n }{8\pi \epsilon_0c^2 r^2} + \frac{1}{8\pi\epsilon_0 c^2 r}\nabla(\hat n \cdot \ddot M \cdot \hat n )\\
&= \frac{1}{4\pi\epsilon_0 cr} \nabla \left(\dot p(t_c) \cdot \hat n\right) +  \frac{1}{8\pi\epsilon_0 c^2 r}\nabla(\hat n \cdot \ddot M \cdot \hat n )\\
\end{align}
$$
#### $\nabla (\dot p(t_c) \cdot \hat n)$
We now have to find $\nabla (\dot p(t_c) \cdot \hat n)$. To do this we will analyse the derivatives of each component like so:
$$
\begin{align}
\frac{\partial \hat n_j}{\partial x_i} &= \frac{\partial}{\partial x_i} \left(\frac{x_j}{r}\right) \\ 
&= \frac{1}{r}\frac{\partial x_j}{\partial x_i} + x_j \frac{\partial}{\partial r}\left(\frac{1}{r}\right) \frac{\partial r}{\partial x_i} \\ 
&= \frac{1}{r}\delta_{ij} + x_j \frac{-1}{r^2} \frac{x_i}{r} \\ 
&= \frac{\delta_{ij}}{r} - \frac{1}{r}\frac{x_ix_j}{r^2} \\ 
&= \frac{\delta_{ij} - \hat n_i\hat n_j}{r} \\ 

\frac{\partial }{\partial x_i} \left(\sum_j \hat n_j \dot p_j(t_c)\right) &= \sum_j \frac{\partial}{\partial x_i} \left(\hat n_j\dot p_j(t_c)\right) \\
&= \sum_j \left(\frac{\partial \hat n_j}{\partial x_i}\dot p_j(t_c) + \hat n_j \frac{\partial \dot p_j}{\partial x_i}\right) \\
&= \sum_j \left(\frac{\delta_{ij} - \hat n_i \hat n_j}{r}\dot p_j(t_c) + \hat n_j \frac{\partial \dot p_j}{\partial t_c}\frac{\partial t_c}{\partial x_i}\right) \\
&= \sum_j \left(\frac{\delta_{ij} - \hat n_i \hat n_j}{r}\dot p_j(t_c) + \hat n_j \ddot p_j(t_c)\frac{-\hat n_i}{c}\right) \\
&= \sum_j \left(\frac{\delta_{ij}}{r}\dot p_j(t_c) - \frac{\hat n_i \hat n_j}{r}\dot p_j(t_c) - \frac{\hat n_j\hat n_i}{c} \ddot p_j(t_c)\right) \\
&= \frac{\dot p_i(t_c)}{r} - \frac{\hat n_i \hat n \cdot \dot p(t_c)}{r} - \frac{\hat n_i \hat n \cdot \ddot p(t_c)}{c} \\

\nabla \left(\hat n \cdot \dot p(t_c)\right) &= \frac{\dot p(t_c)}{r} - \frac{\hat n\cdot \dot p(t_c)}{r} \hat n - \frac{\hat n \cdot \ddot p(t_c)}{c} \hat n \\
\end{align}
$$
Because we will be multiplying by $1/r$ we can also throw out the $1/r$ terms in the above expression to get:
$$
\begin{align}
\nabla \left(\hat n \cdot \dot p(t_c)\right) &= - \frac{\hat n \cdot \ddot p(t_c)}{c} \hat n \\
\end{align}
$$
#### $\nabla (\hat n \cdot \ddot M \cdot \hat n)$
Using tensor notation and throwing out any $1/r$ terms along the way as we will be diving by $r$ we get:
$$
\begin{align}
[\nabla (\hat n \cdot \ddot M(t_c) \cdot \hat n)]_i &= \partial_i(n_jn_k\ddot M_{jk}) \\
&= n_k\ddot M_{jk}\partial_i (n_j) + n_j\ddot M_{jk}\partial_i(n_k) + n_jn_k \partial_i(\ddot M_{jk}) \\
&= n_k\ddot M_{jk}\frac{\delta_{ij} - n_in_j}{r} + n_j \ddot M_{jk} \frac{\delta_{ik} - n_in_k}{r} + n_jn_k\dddot M_{jk} \partial_i(t_c) \\
&= -\frac{n_jn_k\dddot M_{jk}}{c} \frac{\partial r}{\partial r_i} \\
&= -\frac{n_jn_k\ddot M_{jk} n_i}{c} \\
\nabla (\hat n \cdot \ddot M(t_c) \cdot \hat n )&= -\frac{\hat n \cdot \dddot M(t_c) \cdot \hat n }{c}\hat n 
\end{align}
$$
#### Putting it together
Finally we can put this together to get $\nabla \varphi$ to be:
$$
\begin{align}
-\nabla \varphi &=  \frac{1}{4\pi\epsilon_0 cr} \frac{\hat n \cdot \ddot p(t_c)}{c} \hat n + \frac{1}{8\pi\epsilon_0c^2r} \frac{\hat n \cdot \dddot M(t_c) \cdot \hat n}{c}\hat n \\
&= \frac{\hat n \cdot \ddot p(t_c)}{4\pi \epsilon_0 c^2 r} \hat n + \frac{\hat n \cdot \dddot M(t_c) \cdot \hat n}{8\pi\epsilon_0c^3 r}\hat n \\
\end{align}
$$
### Finding $\frac{\partial \vec A}{\partial t}$
$$
\begin{align}
\frac{\partial \vec A}{\partial t} &= \frac{\partial }{\partial t} \left(\frac{\mu_0\dot p(t_c)}{4\pi r} + \frac{\mu_0 \ddot M(t_c) \hat n}{8\pi cr} + \frac{\mu_0 \dot m(t_c) \times \hat n}{4\pi c r}\right) \\
&= \frac{\mu_0\ddot p(t_c)}{4\pi r} + \frac{\mu_0 \dddot M(t_c) \hat n}{8\pi cr} + \frac{\mu_0 \ddot m(t_c) \times \hat n}{4\pi c r}
\end{align}
$$
### Finding $\vec E$
Combining these to get $\vec E$ we get:
$$
\begin{align}
\vec E &= -\nabla \varphi - \frac{\partial \vec A}{\partial t} \\
&= \frac{\hat n \cdot \ddot p(t_c)}{4\pi \epsilon_0 c^2 r} \hat n + \frac{\hat n \cdot \dddot M(t_c) \cdot \hat n}{8\pi\epsilon_0c^3 r}\hat n - \frac{\mu_0\ddot p(t_c)}{4\pi r} - \frac{\mu_0 \dddot M(t_c)\hat n}{8\pi cr} - \frac{\mu_0 \ddot m(t_c) \times \hat n}{4\pi c r} \\
&= \frac{1}{4\pi\epsilon_0 c^2 r}\left[\hat n \cdot \ddot p(t_c) \hat n - \ddot p(t_c) \right] + \frac{1}{8\pi\epsilon_0c^3r}\left[(\hat n \cdot \dddot M(t_c) \cdot \hat n)\hat n  - \dddot M (t_c) \cdot \hat n\right] - \frac{\mu_0 \ddot m(t_c) \times \hat n}{4\pi c r} \\
\end{align}
$$
But this first term can be simplified like so:
$$
\begin{align}
(\hat n \cdot \ddot p(t_c)) \hat n - \ddot p (t_c) &= (\hat n \cdot \ddot p(t_c)) \hat n - (\hat n \cdot \hat n) \ddot p (t_c) \\
&= \hat n \times [\hat n \times \ddot p(t_c)]
\end{align}
$$
and similarly the second term can be simplified like:
$$
\begin{align}
(\hat n \cdot [\dddot M (t_c) \cdot \hat n])\hat n - \dddot M(t_c) \cdot \hat n &= 
(\hat n \cdot [\dddot M (t_c) \cdot \hat n])\hat n - (\hat n \cdot \hat n)[\dddot M(t_c) \cdot \hat n] \\
&= \hat n \times(\hat n \times [\dddot M(t_c) \cdot \hat n])
\end{align}
$$
thus
$$
\begin{align}
\vec E &= \frac{\hat n \times [\hat n \times \ddot p(t_c)]}{4\pi \epsilon_0 c^2 r} + \frac{\hat n \times (\hat n \times [\dddot M (t_c) \cdot \hat n])}{8\pi \epsilon_0 c^2r} + \frac{\mu_0 \hat n \times \ddot m(t_c)}{4\pi c r} \\
\vec E &= \frac{\mu_0\hat n \times [\hat n \times \ddot p(t_c)]}{4\pi r} +\frac{\mu_0 \hat n \times (\hat n \times [\dddot M(t_c) \cdot \hat n ])}{8\pi cr} + \frac{\mu_0 \hat n \times \ddot m(t_c)}{4\pi c r} \\
\end{align}
$$
## Finding $\vec B$
Now we have $\vec E$ lets find $\vec B$:
$$
\begin{align}
\vec B &= \nabla \times \vec A \\
&= \nabla \times \left(\frac{\mu_0\dot p(t_c)}{4\pi r} + \frac{\mu_0 \ddot M(t_c)\hat n}{8\pi c r} + \frac{\mu_0 \dot m(t_c) \times \hat n}{4\pi c r}\right) \\
&= \frac{\mu_0}{4\pi}\nabla \times \left(\frac{\dot p(t_c)}{r}\right) + \frac{\mu_0}{8\pi c}\nabla \times \left(\frac{\ddot M(t_c)\hat n}{r}\right) +  \frac{\mu_0}{4\pi c}\nabla \times \left(\frac{\dot m(t_c) \times \hat n}{r}\right)   \\  
\end{align}
$$
We will now break this up to inspect the terms individually
### First term
We find the first term to be:
$$
\begin{align}
\nabla \times \left(\frac{\dot p(t_c)}{r}\right)&= \frac{1}{r}\nabla \times \dot p(t_c) - \dot p(t_c) \times \nabla \left(\frac{1}{r}\right) \\  
&= \frac{1}{r}\nabla \times \dot p(t_c) + \frac{\dot p(t_c)\times \hat n}{r^2}  \\  
&= \frac{1}{r}\nabla \times \dot p(t_c) \\  
&= \frac{1}{r}\left[-\frac{1}{r}\frac{\partial (r\dot p_\phi)}{\partial r}\hat \theta + \frac{1}{r}\frac{\partial (r\dot p_\theta)}{\partial r}\hat \phi \right]\\  
&= -\frac{\dot p_\phi}{r^2}\hat \theta - \frac{1}{r}\frac{\partial\dot p_\phi}{\partial r}\hat \theta + \frac{\dot p_\theta}{r^2}\hat \phi + \frac{1}{r}\frac{\partial \dot p_\theta}{\partial r}\hat \phi\\  
&= \frac{\ddot p_\phi(t_c)}{cr}\hat \theta - \frac{\ddot p_\theta(t_c)}{cr} \hat \phi\\  
&= \frac{\ddot p(t_c)\times \hat n}{cr}
\end{align}
$$
### Second term
The second term is:
$$
\begin{align}
\nabla \times \left(\frac{\ddot M(t_c)\hat n}{r}\right) &= \frac{1}{r} \nabla \times [\ddot M(t_c) \hat n]- \ddot M(t_c)\hat n \times \nabla\left(\frac{1}{r}\right) \\
&= \frac{1}{r} \nabla \times [\ddot M(t_c) \hat n] + \frac{\ddot M(t_c)\hat n \times \hat n}{r^2} \\
&= \frac{1}{r} \nabla \times [\ddot M(t_c) \hat n] \\
\end{align}
$$
We will now fall back to tensor notation to try and understand this curl operation:
$$
\begin{align}
(\nabla \times [\ddot M(t_c) \hat n])_i &= \epsilon_{ijk} \partial_j [\ddot M(t_c) \hat n]_k \\
&= \epsilon_{ijk} \partial_j (\ddot M_{kl} \hat n_l) \\
&= \epsilon_{ijk} [\partial_j (\ddot M_{kl}) \hat n_l  + \ddot M_{kl} \partial_j (\hat n_l)] \\
&= \epsilon_{ijk} \left[-\frac{\dddot M_{kl}\hat n_l}{c}\frac{\partial r}{\partial r_j}  + \ddot M_{kl} \frac{\delta_{jl} - \hat n_j\hat n_l}{r}\right] \\
&= \epsilon_{ijk} \left[\frac{\ddot M_{kj}}{r}-\frac{\dddot M_{kl}\hat n_l\hat n_j}{c}  - \frac{\ddot M_{kl} \hat n_j\hat n_l}{r}\right] \\
\end{align}
$$
Now, in the original expression  we are dividing be $r$ so we can drop the first and last terms leaving just the central term giving us:
$$
\begin{align}
\left[\nabla \times \left(\frac{\ddot M(t_c)\hat n}{r}\right) \right]_i
&= -\frac{\epsilon_{ijk}\dddot M_{kl}\hat n_l\hat n_j}{cr} \\
&= -\frac{\epsilon_{ijk}\left(\dddot M \hat n\right)_k\hat n_j}{cr} \\
\nabla \times \left(\frac{\ddot M(t_c)\hat n}{r}\right) &= -\frac{\hat n \times (\dddot M\hat n)}{cr} \\
&= \frac{(\dddot M\hat n) \times \hat n}{cr} \\
\end{align}
$$
### Third term
The third term is:
$$
\begin{align}
\nabla \times \left(\frac{\dot m(t_c) \times \hat n}{r}\right) &= \frac{1}{r}\nabla \times \left[\dot m(t_c)\times \hat n\right] - \left[\dot m(t_c) \times \hat n\right] \times \nabla \left(\frac{1}{r}\right) \\
&= \frac{1}{r}\nabla \times \left[\dot m(t_c)\times \hat n\right] + \left[\dot m(t_c) \times \hat n\right] \times \frac{\hat n}{r^2} \\
&= \frac{1}{r}\nabla \times \left[\dot m(t_c)\times \hat n\right] \\
\end{align}
$$
Using tensor notation we get:
$$
\begin{align}
\epsilon_{ijk}\partial_j(\epsilon_{klm}\dot m_l \hat n_m) &= \epsilon_{ijk}\epsilon_{klm} \partial_j(\dot m_l) \hat n_m + \epsilon_{ijk}\epsilon_{klm} \dot m_l \partial_j(\hat n_m) \\
&= -\epsilon_{ijk}\epsilon_{klm} \frac{\ddot m_l\hat n_m}{c} \frac{\partial r}{\partial r_j} + \epsilon_{ijk}\epsilon_{klm} \dot m_l \frac{\delta_{jm} - \hat n_j \hat n_m}{r} \\
&= -\epsilon_{ijk}\epsilon_{klm} \frac{\ddot m_l\hat n_m\hat n_j}{c} + \epsilon_{ijk}\epsilon_{klm} \dot m_l \frac{\delta_{jm} - \hat n_j \hat n_m}{r} \\
\end{align}
$$
We will be dividing by $r$ so the 2nd term vanishes leaving:
$$
\begin{align}
-\epsilon_{ijk}\epsilon_{klm} \frac{\ddot m_l \hat n_m \hat n_j}{c} &= -\epsilon_{ijk}\frac{(\ddot m \times \hat n)_k \hat n_j}{c} \\
&= \frac{(\ddot m \times \hat n)\times \hat n}{c}
\end{align}
$$
which finally allows us to write
$$
\begin{align}
\nabla \times \left(\frac{\dot m(t_c) \times \hat n}{r}\right) &= \frac{1}{r}\nabla \times \left[\dot m(t_c)\times \hat n\right] \\
&= \frac{1}{r}\left[\frac{(\ddot m(t_c) \times \hat n)\times \hat n}{c}\right] \\
&= \frac{(\ddot m(t_c) \times \hat n) \times \hat n}{cr}\\
\end{align}
$$
### Putting it all together
With all of this we can finally write our magnetic field as:
$$
\begin{align}
\vec B &= \frac{\mu_0\ddot p(t_c) \times \hat n}{4\pi cr} + \frac{\mu_0 [\dddot M \cdot \hat n]\times \hat n}{8\pi c^2r} + \frac{\mu_0 [\hat n \times (\hat n \times \ddot m(t_c))]}{4\pi c^2r}
\end{align}
$$
## Relationship between $\vec B$ and $\vec E$
Consider $\frac{1}{c}\hat n \times \vec E$, this gives:
$$
\begin{align}
\frac{1}{c}\hat n \times \vec E &= \frac{1}{c}\hat n \times 
\left[
\frac{\mu_0\hat n \times [\hat n \times \ddot p(t_c)]}{4\pi r}
+ \frac{\mu_0 \hat n \times (\hat n\times [\dddot M(t_c)\cdot\hat n])}{8\pi cr} 
+ \frac{\mu_0 \hat n \times \ddot m(t_c)}{4\pi c r} \right] \\
\end{align}
$$
### Simplifying $\hat n \times [\hat n \times (\hat n \times \vec a)]$
We will briefly explore what happens to $\hat n \times [\hat n \times (\hat n \times \vec a)]$ for some arbitrary $\vec a$ in hopes of simplifying the above expressions.
$$
\begin{align}
\hat n \times [\hat n \times (\hat n \times \vec a)] &= \hat n \times [(\hat n \cdot \vec a)\hat n - (\hat n \cdot \hat n)\vec a]\\
&= (\hat n \cdot \vec a) (\hat n \times \hat n) - \hat n \times \vec a \\
&= (\hat n \cdot \vec a) \vec 0 - \hat n \times \vec a \\
&= \vec a \times \hat n
\end{align}
$$
### Putting it together and interpritations
$$
\begin{align}
&= \frac{1}{c}\left[\frac{\mu_0\ddot p(t_c) \times \hat n}{4\pi r}
+ \frac{\mu_0 [\dddot M\cdot \hat n]\times \hat n}{8\pi cr} 
+ \frac{\mu_0 \hat n \times [\hat n \times \ddot m(t_c)]}{4\pi c r} \right] \\
&= \frac{\mu_0\ddot p(t_c) \times \hat n}{4\pi cr}
+ \frac{\mu_0 [\dddot M\cdot \hat n]\times \hat n}{8\pi c^2r} 
+ \frac{\mu_0 \hat n \times [\hat n \times \ddot m(t_c)]}{4\pi c^2 r} \\
&= \vec B\\
\end{align}
$$
This means that for all radiation the $\vec E$ and $\vec B$ fields travel perpendicular to each other and because all terms have a cross product with $\hat n$ they travel perpendicular to the propigation dirrection aswell
## Finding the Poynting vector
Now lets find the Poynting vector. By definition
$$
\begin{align}
\vec S &= \frac{1}{\mu_0} \vec E \times \vec B \\
&= \frac{1}{\mu_0 c} \vec E \times [\hat n \times \vec E] \\
&= \frac{1}{\mu_0 c} [\hat n (\vec E \cdot \vec E) - \vec E (\hat n \cdot \vec E)] \\
&= \frac{1}{\mu_0 c} [\hat n E^2 - \vec E (0)] \\
&= \frac{E^2}{\mu_0 c} \hat n \\
\end{align}
$$
### Finding $E^2$
Now for $E^2$ we will start by breaking up $\vec E$ into its consituent parts:
$$
\begin{align}
\vec E_p &= \frac{\mu_0 \hat n\times [\hat n \times \ddot p(t_c)]}{4\pi r} \\
\vec E_M &= \frac{\mu_0 \hat n \times [\hat n \times (\dddot M \cdot \hat n)]}{8\pi cr} \\
\vec E_m &= \frac{\mu_0 \hat n \times \ddot m(t_c)}{4\pi c r}
\end{align}
$$
then we get:
$$
\begin{align}
E^2 &= E_p^2 + E_M^2 + E_m^2 + 2\vec E_p\cdot \vec E_M + 2\vec E_p\cdot \vec E_m + 2\vec E_M\cdot \vec E_m
\end{align}
$$
Now we just find all these individual terms:
#### $E_p^2$
$$
\begin{align}
E_p^2 &= \frac{\mu_0^2}{16\pi^2r^2} |\hat n (\hat n \cdot \ddot p) - \ddot p|^2 \\
&= \frac{\mu_0^2}{16\pi^2r^2} \left[|\hat n(\hat n \cdot \ddot p)|^2 - 2(\hat n \cdot \ddot p) (\hat n \cdot \ddot p) + |\ddot p|^2\right] \\
&= \frac{\mu_0^2}{16\pi^2r^2} \left[(\hat n \cdot \ddot p)^2 - 2(\hat n \cdot \ddot p)^2 + \ddot p^2\right] \\
&= \frac{\mu_0^2}{16\pi^2r^2} \left[\ddot p^2 - (\hat n \cdot \ddot p)^2 \right] \\
\end{align}
$$
#### $E_M^2$
$$
\begin{align}
E_M^2 &= \frac{\mu_0^2}{64 \pi^2 c^2 r^2}|\hat n(\hat n \cdot \dddot M \cdot \hat n) - \dddot M \cdot \hat n|^2 \\
&= \frac{\mu_0^2}{64 \pi^2 c^2 r^2}\left[|\hat n|^2(\hat n \cdot \dddot M \cdot \hat n)^2 - 2 (\hat n \cdot \dddot M \cdot \hat n) (\hat n \cdot \dddot M \cdot \hat n) + |\dddot M \cdot \hat n|^2\right] \\
&= \frac{\mu_0^2}{64 \pi^2 c^2 r^2}\left[(\hat n \cdot \dddot M \cdot \hat n)^2 - 2 (\hat n \cdot \dddot M \cdot \hat n)^2 + (\dddot M \cdot \hat n)^2\right] \\
&= \frac{\mu_0^2}{64 \pi^2 c^2 r^2}\left[(\dddot M \cdot \hat n)^2 - (\hat n \cdot \dddot M \cdot \hat n)^2 \right] \\
\end{align}
$$
#### $E_m^2$
$$
\begin{align}
\frac{\mu_0^2}{16 \pi^2 c^2 r^2} |\hat n \times \ddot m|^2 &= \frac{\mu_0^2}{16 \pi^2 c^2 r^2} [|\hat n|^2|\ddot m|^2 - (\hat n \cdot \ddot m)^2] \\
&= \frac{\mu_0^2}{16 \pi^2 c^2 r^2} [\ddot m^2 - (\hat n \cdot \ddot m)^2]
\end{align}
$$
#### $\vec E_p \cdot \vec E_M$
$$
\begin{align}
\vec E_p \cdot \vec E_M &= \frac{\mu_0^2}{32\pi^2 cr^2}[(\hat n \cdot \ddot p)\hat n - \ddot p] \cdot [(\hat n \cdot \dddot M \cdot \hat n) \hat n - \dddot M \cdot \hat n]\\
&= \frac{\mu_0^2}{32\pi^2 cr^2}[(\hat n \cdot \ddot p)(\hat n \cdot \dddot M\cdot \hat n)(\hat n \cdot \hat n) - (\hat n \cdot \dddot M \cdot \hat n)(\ddot p\cdot \hat n) - ] 
\end{align}
$$
<% tp.file.cursor(2) %>
#### $\vec E_p \cdot \vec E_m$
$$
\begin{align}
\vec E_p \cdot \vec E_M &= \frac{\mu_0^2}{16\pi^2 c r^2} [\hat n \times (\hat n \times \ddot p)] \cdot [\hat n \times \ddot m] \\
&= \frac{\mu_0^2}{16\pi^2 c r^2} [\hat n(\hat n \cdot \ddot p) - \ddot p] \cdot [\hat n \times \ddot m] \\
&= \frac{\mu_0^2}{16\pi^2 c r^2} [\hat n(\hat n \cdot \ddot p) \cdot (\hat n \times \ddot m) - \ddot p\cdot (\hat n \times \ddot m)] \\
&= \frac{\mu_0^2}{16\pi^2 c r^2} [0 - \ddot p\cdot (\hat n \times \ddot m)] \\
&= -\frac{\mu_0^2}{16\pi^2 c r^2} \ddot p\cdot (\hat n \times \ddot m) \\
\end{align}
$$
#### $\vec E_M \cdot \vec E_m$
By the exact same logic as with the $\vec E_p\cdot \vec E_M$ case they are perpendicular so their product is $0$
#### The total
Putting all this together gives us:
$$
\begin{align}
E^2 &= \frac{\mu_0^2}{16\pi^2 r^2} [\ddot p^2 - (\hat n \cdot \ddot p)^2] + \frac{\mu_0^2 \dddot M^2}{64 \pi^2 c^2 r^2} + \frac{\mu_0^2}{16 \pi^2 c^2 r^2} [\ddot m^2 - (\hat n \cdot \ddot m)^2] - \frac{\mu_0^2}{16\pi^2 c r^2} \ddot p \cdot (\hat n \times \ddot m)
\end{align}
$$
yay.
### Putting it all together
strap in cause this will be long:
$$
\begin{align}
\vec S &= \frac{\mu_0}{16 \pi^2 c r^2} \left[[\ddot p^2 - (\hat n \cdot \ddot p)^2]\hat n + \frac{(\dddot M\hat n)^2}{4c^2}\hat n + \frac{\ddot m^2 - (\hat n \cdot \ddot m)^2}{c^2}\hat n - \frac{\ddot p \cdot (\hat n \times \ddot m)}{c}\hat n \\ + \frac{\hat n \cdot [\dddot M \hat n ]}{2c}[\hat n \times(\hat n \times \ddot p)] - \frac{\hat n \cdot (\dddot M\hat n)}{4c^2}\dddot M\hat n + \frac{\hat n \cdot [\dddot M \hat n]}{2c^2}[\hat n \times \ddot m]\right]
\end{align}
$$
shesh.
## Finding the radiated energy
To find the radiated power we first have to find the energy flux across a spherical shell centered at the origin. To do this we simply have to do $\frac{\partial P}{\partial \Omega} = (\vec S \cdot \hat n)r^2$.
$$
\begin{align}
(\vec S \cdot \hat n)r^2 &= \frac{\mu_0}{16\pi^2 c} \left[[\ddot p^2 - (\hat n \cdot \ddot p)^2] + \frac{(\dddot M\hat n)^2}{4c^2}+ \frac{\ddot m^2 - (\hat n \cdot \ddot m)^2}{c^2} - \frac{\ddot p \cdot (\hat n \times \ddot m)}{c} \\ + \frac{\hat n \cdot [\dddot M \hat n ]}{2c}[\hat n \times(\hat n \times \ddot p)]\cdot \hat n  - \frac{\hat n \cdot (\dddot M\hat n)}{4c^2}\dddot M\hat n \cdot \hat n + \frac{\hat n \cdot [\dddot M \hat n]}{2c^2}[\hat n \times \ddot m] \cdot \hat n\right] \\
&= \frac{\mu_0}{16\pi^2 c} \left[[\ddot p^2 - (\hat n \cdot \ddot p)^2] + \frac{(\dddot M\hat n)^2}{4c^2}+ \frac{\ddot m^2 - (\hat n \cdot \ddot m)^2}{c^2} - \frac{\ddot p \cdot (\hat n \times \ddot m)}{c} \\ + 0  - \frac{(\hat n \cdot (\dddot M\hat n))^2}{4c^2} + 0\right] \\
&= \frac{\mu_0}{16\pi^2 c} \left[[\ddot p^2 - (\hat n \cdot \ddot p)^2] + \frac{(\dddot M\hat n)^2}{4c^2}+ \frac{\ddot m^2 - (\hat n \cdot \ddot m)^2}{c^2} - \frac{\ddot p \cdot (\hat n \times \ddot m)}{c} \\ - \frac{(\hat n \cdot (\dddot M\hat n))^2}{4c^2} \right] \\
\end{align}
$$
We will now use polar coordinates to integrate over the spherical shell. Let:
- the polar axis be along $\ddot p$
- the azimuthal angle be $\varphi$
- the polar angle be $\theta$
- $\ddot m = (|\ddot m|, \varphi_m, \theta_m)$

That means that the total power is given by:
$$
\begin{align}
P &= \oint (\vec S \cdot \hat n)r^2 d\Omega \\
\frac{16\pi^2 c P}{\mu_0} &= \oint \ddot p^2 - \ddot p^2\cos^2\varphi d\Omega + \frac{1}{4c^2}\oint (\ddot M \hat n)^2 d\Omega \\
&\ \ \ \ + \frac{1}{c^2} \oint \ddot m^2 - \ddot m^2(\sin \varphi \sin \varphi_m \cos(\theta - \theta_m) + \cos \varphi \cos \varphi_m)^2d\Omega \\
&\ \ \ \ - \frac{\ddot p}{c} \oint \sin \varphi \cos \theta \sin \varphi_m\sin\theta_m - \sin\varphi_m \cos\theta_m \sin \varphi \sin\theta d\Omega \\
&\ \ \ \ - \frac{1}{4c^2} \oint  (\hat n \cdot (\dddot M \hat n))^2 d\Omega
\end{align}
$$
We will solve all but the 2nd and final integral as they involve a term that is hard to integrate generally.
### Integral 1
For integral 1 we have:
$$
\begin{align}
\ddot p^2 \int_0^{2\pi}\int_0^\pi (1 - \cos^2 \varphi) \sin \varphi d\varphi d\theta  &= 2\pi\ddot p^2 \left[\int_0^\pi \sin \varphi d\varphi -\int_0^\pi \cos^2 \varphi \sin \varphi d\varphi\right] \\
&= 2\pi\ddot p^2 \left[[-\cos \varphi]_0^\pi +\left[\frac{\cos^3 \varphi}{3}\right]_0^\pi\right]  \\
&= 2\pi\ddot p^2 \left[2 - \frac{2}{3}\right]  \\
&= 2\pi\ddot p^2 \left[\frac{4}{3}\right]  \\
&= \frac{8\pi\ddot p^2}{3}\\
\end{align}
$$
### Integral 3
For integral 3 we have:
$$
\begin{align}
&\ \ \ \ \ \ \oint \ddot m^2 - \ddot m^2(\sin \varphi \sin \varphi_m \cos(\theta - \theta_m) + \cos \varphi \cos \varphi_m)^2d\Omega \\
&= \ddot m^2\int_0^{2\pi}\int_0^\pi \sin\varphi - \sin^3\varphi \sin^2\varphi_m \cos^2(\theta - \theta_m) - 2\sin^2\varphi \cos\varphi \sin\varphi_m\cos\varphi_m\cos(\theta - \theta_m) \\
&\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ - \cos^2\varphi \cos^2\varphi_m \sin\varphi d\varphi d\theta \\
&= \ddot m^2(2\pi)(2) - \ddot m^2\left[\sin^2\varphi_m\int_0^{2\pi}\cos^2(\theta - \theta_m) d\theta\int_0^\pi \sin^3 \varphi d\varphi + \\
2\sin\varphi_m\cos\varphi_m\int_0^{2\pi}\cos(\theta - \theta_m)d\theta\int_0^\pi \sin^2\varphi \cos \varphi d\varphi + \cos^2\varphi_m(2\pi)\int_0^\pi \cos^2\varphi \sin \varphi d\varphi\right] \\
&= 4\pi\ddot m^2 - \ddot m^2\left[\sin^2\varphi_m\left[\frac{\theta - \theta_m}{2} - \frac{\sin(2\theta - 2\theta_m)}{4}\right]_0^{2\pi}\left[-\cos\varphi+\frac{1}{3}\cos^3 \varphi\right]_0^\pi + \\
2\sin\varphi_m\cos\varphi_m\left[\sin(\theta - \theta_m)\right]_0^{2\pi}\left[\frac{\sin^3 \varphi}{3}\right]_0^\pi - 2\pi\cos^2\varphi_m\left[\frac{\cos^3\varphi}{3}\right]_0^\pi\right] \\
&= 4\pi\ddot m^2 - \ddot m^2\left[\sin^2\varphi_m\left[\pi - 0\right]\left[2 -\frac{2}{3}\right] + 2\sin\varphi_m\cos\varphi_m\left[0\right]\left[0\right] + 2\pi\cos^2\varphi_m\left[\frac{2}{3}\right]\right] \\
&= 4\pi\ddot m^2 - \ddot m^2\left[\frac{4\pi}{3}\sin^2\varphi_m + \frac{4\pi}{3}\cos^2\varphi_m\right] \\
&= 4\pi\ddot m^2 - \frac{4\pi\ddot m^2}{3}\\
&= \frac{8\pi\ddot m^2}{3}\\
\end{align}
$$
### Integral 4
We will now solve integral 4:
$$
\begin{align}
&\ \ \ \ \ \ \oint \sin \varphi \cos \theta \sin \varphi_m\sin\theta_m - \sin\varphi_m \cos\theta_m \sin \varphi \sin\theta d\Omega \\
&= \sin\varphi_m\oint \sin\varphi(\sin \theta_m\cos\theta - \sin\theta\cos\theta_m) d\Omega \\
&= -\sin\varphi_m\oint \sin\varphi\sin(\theta - \theta_m) d\Omega \\
&= -\sin\varphi_m\int_0^{2\pi}\int_0^\pi \sin^2\varphi\sin(\theta - \theta_m) d\varphi d\theta \\
&= -\sin\varphi_m\int_0^{2\pi}\sin(\theta - \theta_m)d\theta\int_0^\pi \sin^2\varphi d\varphi \\
&= -\sin\varphi_m(0)\int_0^\pi \sin^2\varphi d\varphi \\
&= 0
\end{align}
$$
### Putting it together
With these integrals we get the total radiated power to be:
$$
\begin{align}
P &= \frac{\mu_0}{16\pi^2 c} \left[\frac{8\pi \ddot p^2}{3} + \frac{1}{4c^2}\oint (\dddot M \hat n)^2 d\Omega + \frac{8\pi \ddot m^2}{3c^2} - \frac{1}{4c^2} \oint (\hat n \cdot (\dddot M \hat n))^2 d\Omega \right]
\end{align}
$$
