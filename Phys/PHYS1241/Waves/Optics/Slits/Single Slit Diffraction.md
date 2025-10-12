For slits on the order of magnitude of a wave's wavelength a diffraction pattern is produced.
## Formulas
### Angle dependent
![[Pasted image 20250808110328.png]]
First we can consider two light rays, one from the side of the slit and one from the middle of the slit which mathematically is apparently identical to doing this over all points. Using similar methods as the [[Young's Interference Experiment|double slit]] one can approximate rays of light as parallel to each other as so.
![[Pasted image 20250808111248.png]]
similarly to the double slit we get that $\Delta PLD = \frac{a}{2}sin(\theta)$ which means our phase difference is $\Delta \Phi = \frac{2 \pi a}{\lambda 2} sin(\theta)$ giving us that the minimums occur when $$\begin{align}
m\pi &= \frac{2 \pi a} {2 \lambda} sin(\theta) \\
m &= \frac{a}{\lambda}sin(\theta) \\
a sin(\theta) &= m\lambda
\end{align}$$
**NOTE**: m in this formula is for the mth order ***dark*** spot but in the [[Young's Interference Experiment|double slit]] it is for the mth order ***bright*** spot.

We can also get the mth order bright spots by using $m - \frac{1}{2}$ instead making the formula $$asin(\theta) = \left(m - \frac{1}{2}\right)\lambda.$$
### Distance dependence
Noting that $tan(\theta) = \frac{y}{D}$ we can use the small angle approximation to make the substitution $sin(\theta) \approx tan(\theta)$ to get $$
\begin{align}
a \frac{y}{D} &= m \lambda \\
a y &= m \lambda D
\end{align}
$$
for dark spots and
$$\begin{align}
a y &= \left(m - \frac{1}{2} \right) \lambda D
\end{align}$$
for light spots.
### Intensity
Using the method of [[Phasors]] we can add the electric fields together to get the arc of a circle.
![[Pasted image 20250808114048.png]]![[Pasted image 20250808114138.png]]
where $\Phi$ is the total angle change so has the formula $\Phi = \left(\frac{2\pi}{\lambda}\right)asin(\theta)$ 
Using this we get that $\alpha = \left(\frac{\pi}{\lambda}\right)asin(\theta)$.  Inspecting the arc length of the circle we get $$
\begin{align}
E_m &= R2\alpha \\
R &= \frac{E_m}{2\alpha}
\end{align}
$$ and from the triangle we get $$
\begin{align}
sin(\alpha) &= \frac{E_0}{2R} \\
sin(\alpha) &= \frac{E_0 2\alpha}{2E_m} \\
\frac{E_0}{E_m} &= \frac{sin(\alpha)}{\alpha}
\end{align}
$$ which we can square to find the relative intensity for any angle $\theta$ $$
\begin{align}
\left(\frac{E_0}{E_m}\right)^2 &= \left(\frac{sin(\alpha)}{\alpha}\right)^2 \\
\frac{I(\theta)}{I_m} &= \frac{sin^2(\alpha)}{\alpha^2} \\
I(\theta) &= I_m\frac{sin^2(\alpha)}{\alpha^2}
\end{align}
$$
where $\alpha = \frac{\pi a}{\lambda} sin(\theta)$