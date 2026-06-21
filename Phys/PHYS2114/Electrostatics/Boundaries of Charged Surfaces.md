Consider a sheet of charge. If the sheet is not flat then zoom in onto the sheet until its flat. We then can construct a pillbox on the surface with a depth of $\varepsilon$ extending through the surface and face area $A$. Because the sheet is roughly flat we can assume that $\vec E$ is normal to the surface and thus by Gauss's law:
$$
\begin{align}
\oint_P \vec E \cdot d\vec A &= \frac{q_{\text{enc}}}{\epsilon_0} \\
E_{\text{above}}^\perp A - E_{\text{below}}^\perp A&= \frac{\sigma A}{\epsilon_0} \\
E_{\text{above}}^\perp - E_{\text{below}}^\perp &= \frac{\sigma }{\epsilon_0} \\
\end{align}
$$
Then considering a simple line integral loop through the surface:
$$
\begin{align}
\oint \vec E \cdot d\vec l &= \iint(\nabla \times \vec E) d \vec A \\
 &= \iint0 d \vec A \\
 E^\parallel_{\text{above}}l - E^\parallel_{\text{below}}l&= 0 \\
 E^\parallel_{\text{above}} - E^\parallel_{\text{below}}&= 0 \\
\end{align}
$$
So there is no tangential discontinuity therefore the discontinuity across the surface of a charged object is given by:
$$
\begin{align}
\vec E_{\text{above}} - \vec E_{\text{below}} &= \frac{\sigma }{\epsilon_0} \hat n \\
\end{align}
$$
