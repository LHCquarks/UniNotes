## Single slit
Let our aperture be an infinity tall single slit with width $w$, we get the aperture function to be:
$$
\begin{align}
f(x, y) &= \Pi\left(\frac{x}{w}\right)
\end{align}
$$
Because the aperture function is constant W.R.T $y$ we can ignore it and only worry about the 1d case and thus via the Fraunhofer diffraction technique we get the far field diffraction pattern to be:
$$
\begin{align}
\phi(s) &= \mathcal F\left\{\Pi\left(\frac{x}{w}\right)\right\} \\
&= w\mathcal F\{\Pi\}(ws) \\
&= w\frac{\sin(\pi w s)}{\pi ws} \\
&= \frac{\sin(\pi w s)}{\pi s} \\
I &= \left(\frac{\sin(\pi w s)}{\pi s}\right)^2 \\
\end{align}
$$
where $s = \frac{\sin \theta}{\lambda}$.
## Ideal double slit
For an ideal double slit (width of slits is $0$) we have the aperture function:
$$
\begin{align}
f(x, y) &= \delta(|x| - d)
\end{align}
$$
and thus the far field deffraction pattern is:
$$
\begin{align}
\phi(s) &= \mathcal F\{\delta(|x| - d)\} \\
&= \mathcal F\{\delta(x + d)\} + \mathcal F\{\delta(x - d)\} \\
&= e^{2\pi isd}\mathcal F\{\delta(x)\} + e^{-2\pi i sd}\mathcal F\{\delta(x)\} \\
&= e^{2\pi isd}\mathcal + e^{-2\pi i sd} \\
&= 2\cos(2\pi sd) \\

\end{align}
$$
<% tp.file.cursor(2) %>
