Say we have a single particle moving along a path $\vec r_q(t')$, what is the field, radiation and potential of this particle?
We get:
$$
\begin{align}
\rho(\vec r', t') &= q\delta(\vec r' - \vec r_q(t')) \\
\vec J (\vec r', t') &= q v(t') \delta (\vec r' - \vec r_q(t'))
\end{align}
$$
## Finding the potentials
We will use the green's function for the potentials before simplifying time integral:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{1}{4\pi\epsilon_0} \int_{\mathbb R^3} \int_{\mathbb R} \frac{\rho(\vec r', t')}{|\vec r - \vec r'|}\delta\left(t - t' - \frac{|\vec r - \vec r'|}{c}\right) dt' d^3r'\\
&= \frac{q}{4\pi\epsilon_0} \int_{\mathbb R^3} \int_{\mathbb R} \frac{\delta(\vec r' - \vec r_q(t'))}{|\vec r - \vec r'|}\delta\left(t - t' - \frac{|\vec r - \vec r'|}{c}\right) dt' d^3r'\\
&= \frac{q}{4\pi\epsilon_0} \int_{\mathbb R} \frac{1}{|\vec r - \vec r_q(t')|}\delta\left(t - t' - \frac{|\vec r - \vec r_q(t')|}{c}\right) dt'\\
\end{align}
$$
Now, letting 
$$
\begin{align}
R(t') &= |\vec r - \vec r_q(t')| \\
g(t') &= t - t' - R(t') / c
\end{align}
$$
this simplifies to
$$
\begin{align}
\varphi(\vec r, t) &= \frac{q}{4\pi\epsilon_0} \int_{\mathbb R} \frac{\delta[g(t')]}{R(t')} dt'\\
\end{align}
$$
We now use the identity:
$$
\begin{align}
\delta[g(t')] &= \sum_i \frac{\delta(t' - t_i)}{|g'(t_i)|}
\end{align}
$$
where $t_i$ are the roots of $g(t')$. Taking the derivative of $g(t')$ we find:
$$
\begin{align}
g'(t') &= -1 - \frac{1}{c}\frac{dR}{dt'} \\
&= -1 + \frac{\hat n \cdot \vec v(t')}{c} \\
&= \hat n \cdot \vec \beta(t') - 1
\end{align}
$$
but because for a massive particle $\beta < 1$ we have that $g'(t') < 0$ and thus $g(t')$ can only have one root. Call this root $t_r$, that is $t = t_r + R(t_r) / c$. Further, denote $\kappa(t') = 1 - \hat n \cdot \vec \beta(t')$  

With this we have:
$$
\begin{align}
\varphi(\vec r, t) &= \frac{q}{4\pi \epsilon_0} \frac{1}{\kappa(t_r) R(t_r)}
\end{align}
$$
Similarly, we do the same sort of thing for $\vec A$ to get:
$$
\begin{align}
\vec A(\vec r, t) &= \frac{\mu_0}{4\pi} \int_{\mathbb R^3} \int_{\mathbb R} \frac{\vec J(\vec r', t')}{|\vec r - \vec r'|} \delta\left(t - t' - \frac{|\vec r - \vec r'|}{c}\right) dt' d^3 r' \\
&= \frac{\mu_0q}{4\pi} \int_{\mathbb R^3} \int_{\mathbb R} \frac{\vec v(t')\delta(\vec r' - \vec r_q(t'))}{|\vec r - \vec r'|} \delta\left(t - t' - \frac{|\vec r - \vec r'|}{c}\right) dt' d^3 r' \\
&= \frac{\mu_0q}{4\pi} \int_{\mathbb R} \frac{\vec v(t')}{|\vec r - \vec r_q(t')|} \delta\left(t - t' - \frac{|\vec r - \vec r_q(t')|}{c}\right) dt' \\
&= \frac{\mu_0q}{4\pi} \int_{\mathbb R} \frac{\vec v(t')}{R(t')} \delta\left(g(t')\right) dt' \\
&= \frac{\mu_0q}{4\pi} \frac{\vec v(t_r)}{R(t_r)\kappa(t_r)}\\
\end{align}
$$

These are called the Lienard-Wiechert potentials.
## Finding $\vec E$
We will need to start differentiating our fields so lets get some basic derivatives out of the way first.
$$
\begin{align}
\frac{dR}{dt_r}  &= -\hat n \cdot \vec v\\
\frac{dt}{dt_r} &= 1 + \frac{1}{c}\frac{dR}{dt_r} \\
&= 1 - \frac{1}{c}\hat n \cdot \vec v \\
&= \kappa \\
\frac{dt_r}{dt} &= \frac{1}{\kappa} \\
\frac{d\hat n}{dt_r} &= \frac{d}{dt_r}\left(\frac{\vec R}{R}\right) \\
&= \frac{1}{R}\frac{d\vec R}{dt_r} - \frac{\vec R}{R^2} \frac{dR}{dt_r} \\
&= - \frac{\vec v}{R} + \frac{\hat n }{R} \hat n \cdot \vec v \\
&= \frac{c}{R} [(\hat n \cdot \vec \beta)\hat n - \vec \beta] \\
&= \frac{c}{R} [\hat n \times (\hat n \times \vec \beta)] \\
\nabla R &= \frac{dR}{dt_r}
\end{align}
$$

