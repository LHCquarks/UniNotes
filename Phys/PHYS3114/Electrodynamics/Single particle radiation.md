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
\frac{q}{4\pi\epsilon_0} \int_{\mathbb R} \frac{\delta[g(t')]}{R(t')} dt'\\
\end{align}
$$
We now use the identity:
$$
\begin{align}
\delta[g(t')] &= \sum_i \frac{\delta(t' - t_i)}{|g'(t_i)|}
\end{align}
$$
where $t_i$ are the roots of $g(t')$. The roots of $g(t')$ are given by:
$$
\begin{align}
g'(t') &= -1 - \frac{1}{c}\frac{dR}{dt'} \\
0 &= -1 + \frac{\hat n \cdot \vec v(t')}{c} \\
\hat n \cdot \vec v(t') &= c
\end{align}
$$
<% tp.file.cursor(2) %>