When light is incident onto a target new wavelengths of light are emitted for different angle deflections off the block. In a metaphorical sense it is as if these wavelengths have been scattered.
![[Pasted image 20250814122850.png]]
The difference in wavelength between the incident ray and the reflected ray is known as the Compton shift and is given by the formula $\Delta \lambda = \frac{h}{mc}(1-cos(\Phi))$. In reality, many different wavelengths will be measured as some light rays hit electrons whilst others hit protons and neutrons causing different Compton shifts.
## Derivation

consider the diagram:
![[Pasted image 20250814122929.png]]
Considering the the [[Vector Tensor approach#Energy momentum vector|4-vector for momentum]] we can rewrite the relativistic dispersion relation as $$
\begin{align} 
E^2 &= \vec{p}^2c^2+m^2c^4 \\
0 &= \left(\frac{E}{c}\right)^2 - \vec{p}^2 - m^2c^2 \\
0 &= \vec{p}_\mu \vec{p}^\mu - m^2c^2.
\end{align}$$ 
Using momentum conservation we get
$$
\begin{align} 
\vec{k} + \vec{p} &= \vec{k}' + \vec{p}' \\
\vec{p}' &= \vec{k} + \vec{p} - \vec{k}'
\end{align}
$$
which we can substitute into the relativistic dispersion relation to get
$$
\begin{align}
0 &= (\vec{k} + \vec{p} - \vec{k}')_\mu (\vec{k} + \vec{p} - \vec{k}')^\mu - m^2c^2 \\
0 &= \vec{k}_\mu \vec{k}^\mu + \vec{k}'_\mu \vec{k}'^\mu + \vec{p}_\mu \vec{p}^\mu + 2\vec{k}_\mu \vec{p}^\mu - 2 \vec{k}_\mu \vec{k}'^\mu - 2\vec{k}'_\mu \vec{p}^\mu
- m^2c^2 \\
0 &= \vec{k}_\mu \vec{k}^\mu + \vec{k}'_\mu \vec{k}'^\mu + \vec{p}_\mu \vec{p}^\mu + 2\vec{p}_\mu (\vec{k} - \vec{k}')^\mu - 2 \vec{k}_\mu \vec{k}'^\mu - m^2c^2 \\
\end{align}
$$
Now, using the fact that for a photon $E_\gamma^2 = \vec{k}^2_3c^2 \implies 0 = E_\gamma^2/c^2 - \vec{k}_3 \implies \vec{k}_\mu \vec{k}^\mu = 0$  where $\vec{k}_3$ is the 3 dimensional momentum vector not the 4-vector. Using similar logic we can also show that for an electron, $\vec{p}_\mu \vec{p}^\mu = m_e^2 c^2$. 
Subbing these two into the dispersion relation we get 
$$
\begin{align}
0 &= 0 + 0 + m_e^2 c^2 + 2\vec{p}_\mu (\vec{k} - \vec{k}')^\mu - 2 \vec{k}_\mu \vec{k}'^\mu - m_e^2c^2 \\
0 &= 2\vec{p}_\mu (\vec{k} - \vec{k}')^\mu - 2 \vec{k}_\mu \vec{k}'^\mu \\
0 &= \vec{p}_\mu (\vec{k} - \vec{k}')^\mu - \vec{k}_\mu \vec{k}'^\mu \\
0 &= \begin{pmatrix} m_ec^2 / c & 0 & 0 & 0 \end{pmatrix} \begin{pmatrix}
E_\gamma / c - E_\gamma' / c \\ k_1 - k_1' \\ k_2 - k_2' \\ k_3 - k_3'
\end{pmatrix} - \vec{k}_\mu \vec{k}'^\mu \\
0 &= m_e(E_\gamma - E_\gamma') - \vec{k}_\mu \vec{k}'^\mu \\
\end{align}
$$
Noting that $\vec{k}_\mu = \begin{pmatrix}1 & 0 & 0 & 0 \\ 0 & -1 & 0 & 0 \\ 0 & 0 & -1 & 0 \\ 0 & 0 & 0 & -1 \end{pmatrix}\vec{k}^\mu$  and $\vec{k}^\mu = \begin{pmatrix} E_\gamma / c \\ k_1 \\ k_2 \\ k_3 \end{pmatrix}$ we get $\vec{k}_\mu = \begin{pmatrix} E_\gamma / c \\ -k_1 \\ -k_2 \\ -k_3 \end{pmatrix}$.
Substituting these values back into the dispersion relation we get 
$$
\begin{align}
0 &= m_e(E_\gamma - E_\gamma') - \frac{E_\gamma E_\gamma'}{c^2} + \vec{k}_3\vec{k}_3' \\
0 &= m_e(E_\gamma - E_\gamma') - \frac{E_\gamma E_\gamma'}{c^2} + |\vec{k}_3||\vec{k}_3'|cos(\Phi) \\
0 &= m_e(E_\gamma - E_\gamma') - \frac{E_\gamma E_\gamma'}{c^2} + |E_\gamma/c||E_\gamma' / c|cos(\Phi) \\
0 &= m_e(E_\gamma - E_\gamma') - \frac{E_\gamma E_\gamma'}{c^2}(1 - cos(\Phi)) \\
\frac{E_\gamma E_\gamma'}{c^2}(1 - cos(\Phi)) &= m_e(E_\gamma - E_\gamma') \\
1 - cos(\Phi) &= m_ec^2(1/E_\gamma' - 1/E_\gamma) \\

\end{align}
$$
Using $E_\gamma = \frac{hc}{\lambda}$  we get 
$$
\begin{align}
1 - cos(\Phi) &= m_ec^2\left(\frac{\lambda'}{hc} - \frac{\lambda}{hc}\right) \\
1 - cos(\Phi) &= \frac{m_ec^2}{hc}(\lambda'-\lambda) \\
1 - cos(\Phi) &= \frac{m_ec}{h}(\Delta \lambda) \\
\Delta \lambda &= \frac{h}{m_e c} (1 - cos(\Phi))  \\
\end{align}
$$
