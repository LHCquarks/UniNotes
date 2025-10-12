---
aliases:
  - double slit
---
Young took sun light, put it through a single slit to make it coherent and then passed it through a double slit and observed an interference pattern. This was smoking gun for the wave model of light so became a very famous experiment.

Diagram: ![[Pasted image 20250806191742.png]]
## The modern experiment
Instead of using sunlight passed through a single slit we can instead use a lazer which produces much cleaner results.

## Equations
### Angle dependent
Consider the following diagram: ![[Pasted image 20250806192044.png]]
Because $D >> d$ we can approximate the two rays as parallel allowing us to zoom in and get
![[Pasted image 20250806192236.png]]
where the part coloured in green is the [[Path length difference]] of the two rays. Inspecting the diagram we get that $sin(\theta) = \frac{\Delta PLD}{d}$. Only considering when the rays are in phase we get that $\Delta PLD = m \lambda$ where $m$ is an integer, which we can substitute into the previous equation to get $sin(\theta) = \frac{m\lambda}{d}$ which can be written as 
$$
dsin(\theta) = m\lambda.
$$

If we instead wanted the minimums of intensity we get  $$dsin(\theta)=(m-\frac{1}{2})\lambda$$ where again $m$ is an integer.

### Distance dependent
By using the small angle approximation $sin(\theta) \approx tan(\theta)$ we get that $sin(\theta) \approx \frac{y}{D}$ which turns the above expressions into $$d y = m \lambda D$$ for the maximum intensities and $$d y = (m-\frac{1}{2})\lambda D$$
for the minimum intensities.
### Intensity given angle
When the size of the slits are negligible we can use the method of [[Phasors#Sum of two waves off by a phase of $ Phi$|phasors]] to get that
$$E=2E_0cos\left(\frac{\Phi}{2}\right)$$
where $\Phi$ is the phase difference of the two light rays and equals $\Phi = 2 \pi m = \frac{2 \pi d sin(\theta)}{\lambda}$ . Using the definition of intensity $I \alpha {E}_{max}^2$ we get that $$I \alpha 4E_0cos^2\left(\frac{\Phi}{2}\right).$$ Finally, comparing the intensity to the maximum intensity and writing $\frac{\Phi}{2}$ as $\alpha$ we get
$$I(\theta) = I_{max}cos^2(\alpha)$$
where $\alpha = \frac{\pi d sin(\theta)}{\lambda}$.

When the size of the slits does matter we just multiply by the [[Single Slit Diffraction#Intensity|single slit intensity formula]] which gives $$I(\theta) = I_{max}cos^2(\alpha)\left( \frac{sin(\beta/2)}{\beta/2}\right)$$ where as with the equation above $\alpha = \frac{\pi d sin(\theta)}{\lambda}$ and $\beta = \frac{2 \pi a sin(\theta)}{\lambda}$.