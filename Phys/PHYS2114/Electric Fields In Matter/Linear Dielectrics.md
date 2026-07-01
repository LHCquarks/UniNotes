Even given $\vec D$ we can not find $\vec E$ without $\vec P$ and so finding $\vec P$ for various materials will be very helpful. As it turns out it is an extreamly good approximation to say that $\vec P$ varies linearly with $\vec E$:
$$
\begin{align}
\vec P &= \epsilon_0 \chi_e \vec E
\end{align}
$$
where $\chi_e$ is the **electric susceptibility** of the material. Materials that obey this are called **linear dielectrics**.

With this we can find a new formula for $\vec D$:
$$
\begin{align}
\vec D &= \epsilon_0 \vec E + \vec P \\
&= \epsilon_0 \vec E + \epsilon_0\chi_e\vec E \\
&= \epsilon_0 (1 + \chi_e)\vec E \\
\end{align}
$$
Thus $\vec D$ is also linearly proportional to $\vec E$ by a factor of $\epsilon_0 (1 + \chi_e)$ something we sometimes rewrite as $\epsilon$ the electric permittivity of the material or $\epsilon_0 \epsilon_r$ where $\epsilon_r$ is the relative permittivity of the material.