## Sheets
Consider a sheet of charge (any 2d surface with charge on it). We can then consider a little rectangular region with area $A$ parallel to the surface that slices through the surface with a length of $\varepsilon$.

Using Gauss's law and stating that the contribution of the parallel electric field is negligible due to the infinitesimal size of $\varepsilon$ we get:
$$
\begin{align}
\oint \vec E \cdot d\vec A &= \frac{q_{\text{enc}}}{\epsilon_0} \\
 E^\perp_{\text{above}} A - E^\perp_{\text{below}} A&= \frac{A\sigma}{\epsilon_0} \\
 E^\perp_{\text{above}} - E^\perp_{\text{below}} &= \frac{\sigma}{\epsilon_0} \\
\end{align}
$$
Then considering a simple line integral loop through the surface:
$$
\begin{align}
\oint \vec E \cdot d\vec l &= \iint(\nabla \times \vec E) d \vec A \\
 &= \iint0 d \vec A \\
 E^\parallel_{\text{above}}l - E^\parallel_{\text{below}}&= 0 \\
\end{align}
$$
And thus:
$$
\begin{align}
\vec E_{\text{above}} - \vec{E}_{\text{below}} &= \frac{\sigma}{\epsilon_0}\hat n
\end{align}
$$
This means on the surface the electric field is discontinuous, however, because they are only different by a constant the voltage is continuous.