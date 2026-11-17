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
We can then use the Taylor expansion for $(1 + x)^{1/2} = 1 + \frac{1}{2}x - \frac{1}{4}x^2 + \mathcal O(x^3)$ and the fact that $\mathcal O(x) = \mathcal O(1/r)$ to get:
$$
\begin{align}
R &= r\left[1 + \frac{1}{2}\left(\left(\frac{r'}{r}\right)^2 - 2\left(\frac{r'}{r}\right)\cos \alpha\right) - \frac{1}{4}\left(\left(\frac{r'}{r}\right)^2 - 2\left(\frac{r'}{r}\right)\cos\alpha\right)^2 + \mathcal O\left(\frac{1}{r^3}\right)\right] \\
&= r + \frac{(r')^2}{2r} - r'\cos \alpha - \frac{r}{4}\left(\left(\frac{r'}{r}\right)^4  - 4\left(\frac{r'}{r}\right)^3 +  4\left(\frac{r'}{r}\right)^2\cos^2\alpha\right) + \mathcal O\left(\frac{1}{r^2}\right) \\
&= r + \frac{(r')^2}{2r} - r'\cos \alpha - \frac{(r')^4}{4r^3}  + \frac{(r')^3}{r^2} -  \frac{(r')^2}{r}\cos^2\alpha + \mathcal O\left(\frac{1}{r^2}\right) \\
&= r + \frac{(r')^2}{2r} - r'\cos \alpha -  \frac{(r')^2}{r}\cos^2\alpha + \mathcal O\left(\frac{1}{r^2}\right) \\
\end{align}
$$
Wonderful, we will store this for when we expand $\rho$ and $\vec J$.
## Expanding $\rho$ and $\vec J$
Start with