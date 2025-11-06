## Definition
Complex polynomials are defined in the same way as real polynomial except that $p: \mathbb{C} \rightarrow \mathbb{C}$ 
$$
p(z) = a_dz^d + ... + a_1z+a_0 \tag{1}
$$
## Similarities
### Degree
The degree of a complex polynomial is the same as it's real counterpart (the exponent of the highest term), $d$ in the case of the above definition
### Combinations 
The:
- Sums 
- Differences
- Products
- Compositions
of polynomials remain polynomials
### Polynomial division and partial fractions
We can still write 
$$
\frac{p(z)}{q(z)} = s(z) + \frac{r(z)}{q(z)}
$$
for any polynomial $p(z)$ and $q(z)$.
## Differences
### Fundamental theorem of algebra
In the complex world every non constant polynomial can be factorized such that
$$
\begin{align}
p(z)=c\prod_{j=1}^{d}(z-\alpha_j) \tag{2}
\end{align}
$$
Where $\alpha_j$ is a root of the polynomial
### Full partial fraction decomposition
Due to the fundamental theorem of algebra and partial fraction decomposition we are able to reduce a division of polynomials into a single polynomial + a sum of linear reciprocal terms.
$$
\frac{p(z)}{q(z)} = s(z) + \frac{a_1}{f_1(z)} + \frac{a_2}{f_2(z)} + ... + \frac{a_n}{f_n(z)}
$$
where $f_i$ is a linear polynomial

### Range
The range of any non-constant complex polynomial is the entire complex plane!
Consider an arbitrary $w, z \in \mathbb{C}$ and the polynomial $p(z)$. Now consider the polynomial $p(z) - w$ which must have roots by $(2)$ thus we get
$$
\begin{align}
p(z) - w &= 0 \\
p(z) &= w. \\
\end{align}
$$
So for every $w$ there exists a $z\in \mathbb{C}$ such that $p(z) = w$, hence the range of a complex polynomial is the entire complex plane!