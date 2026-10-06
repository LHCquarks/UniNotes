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
f(x, y) &= \delta(x + d/2) + \delta(x - d/2)
\end{align}
$$
and thus the far field diffraction pattern is:
$$
\begin{align}
\phi(s) &= \mathcal F\{\delta(x + d/2)\} + \mathcal F\{\delta(x - d/2)\} \\
&= e^{\pi isd}\mathcal F\{\delta(x)\} + e^{-\pi i sd}\mathcal F\{\delta(x)\} \\
&= e^{\pi isd}\mathcal + e^{-\pi i sd} \\
&= 2\cos(\pi sd) \\
I &=  4 \cos^2(\pi sd)

\end{align}
$$
## Real double slits
We can construct the aperture function through convolutions with dirac delta functions:
$$
\begin{align}
f(x) &= \Pi\left(\frac{x}{w}\right) * [\delta(x + d/2) + \delta(x - d/2)]
\end{align}
$$
These have the form of the two we solved before and thus FT of this will be the product of the two:
$$
\begin{align}
\phi(s) &= \mathcal F\{f\} \\
&= \frac{\sin(\pi w s)}{\pi s} \cdot 2\cos(\pi sd) \\
I &=  \frac{4}{\pi^2 s^2}\sin^2(\pi w s)\cos^2(\pi ds)
\end{align}
$$
## Diffraction Gratings
For a diffraction grating that has:
- slits with width $w$
- a gap between slits of $d$
- a total number of slits $n$
we get the aperture function:
$$
\begin{align}
f(x) &= \left(\Pi\left(\frac{x}{w}\right) * \text{array}\left(\frac{x}{d}\right)\right) \cdot\Pi\left(\frac{x}{nd}\right)
\end{align}
$$
Applying the FT we find:
$$
\begin{align}
\phi(s) &= \mathcal F\{f\} \\
&= \mathcal F\left\{\Pi\left(\frac{x}{w}\right) * \text{array}\left(\frac{x}{d}\right)\right\} * \mathcal F\left\{\Pi\left(\frac{x}{nd}\right)\right\} \\
&= \left[\mathcal F\left\{\Pi\left(\frac{x}{w}\right)\right\} \cdot  \mathcal F\left\{\text{array}\left(\frac{x}{d}\right)\right\} \right]* \mathcal F\left\{\Pi\left(\frac{x}{nd}\right)\right\} \\
&= \left[\frac{\sin(\pi w s)}{\pi s} \cdot d\text{ array}(ds) \right] * dn\frac{\sin(\pi dsn)}{\pi dsn} \\
&= \frac{d}{\pi^2}\left[\frac{\sin(\pi w s)}{s} \cdot \text{ array}(ds) \right] * \frac{\sin(\pi dsn)}{s} \\
\end{align}
$$
the first term ($\frac{\sin(\pi w s)}{s} \cdot \text{array}(ds)$) produces a bunch of Dirac delta functions with area given by $\frac{\sin(\pi w s)}{s}$ and so the convolution simply duplicates the function $\frac{\sin(\pi dns)}{s}$ and multiplies by $\frac{\sin(\pi w s)}{s}$ ( creating an envelope) to produce the curve below:
![[diffractionGrating 1.gif]]
## Resolving power of diffraction gratings
Diffraction gratings arre often used to separate wavelengths of light to analyze them individually but what is the resolving power of these things?

We look to the first order peak and notice that they happen at the first (non-zero) peak of our $\text{array}$ function and thus $1 = ds = \frac{d\sin\theta}{\lambda}$ so $\sin\theta = \frac{\lambda}{d}$. 

Taking the small angle approximation we get $\theta = \frac{\lambda}{d}$. Now, for two intensity patterns to be resolvable we say that the peak of one must be past the first minimum of the other. Bellow shows the cutoff point for resolve-ability:


The distance between the two peak is thus $\Delta \theta = \frac{\Delta \lambda}{d}$. The distance from a peak to a minimum is the same as asking what the distance from the center to the first minimum of $\frac{\sin(\pi dsn)}{s}$ is, which can easily be seen to be $1 = dsn$  and thus $1 = \frac{dn\sin(\Delta\theta)}{\lambda} = \frac{dn\Delta\theta}{\lambda}$. Finally, we can equate $\Delta \theta$ to get:
$$
\begin{align}
1 &= \frac{dn\Delta \lambda}{d\lambda} \\
\frac{\Delta \lambda}{\lambda} &= \frac{1}{n}
\end{align}
$$
This is the **Rayleigh Criterion** and says that the resolving power $\Delta \lambda$ is only dependent on the number of slits we use and the average wavelength of light we are measuring.
