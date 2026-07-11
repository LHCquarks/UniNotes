Topics to cover:
## Math of QM
### State vector spaces are cool
### Define the duel space
### Bra-ket notation
### Inner product space
1. $\braket{v|w} = \braket{w|v}^*$
2. $\braket{v|v} \ge 0$
	- We also need $\braket{v|v} = 0$ iff $\ket v = \ket 0$
3. $\braket{u|av + bw} = a\braket{u|v} + b\braket{u|w}$
- Length
- Exercise: proof of linearity of the bra
$$
\begin{align}
A &= \braket{au + bv | w} \\
&= \braket {w | au + bv}^* \tag {1}\\ 
&= a^*\braket{w|u}^* + b^*\braket{w|v}^* \tag{3}\\
&=  a^*\braket{u|w} + b^*\braket{v|w} \\
\end{align}
$$
- Orthogonality
- Inner product for complex vectors
### Operators
Exercise:
apply the mysterious operator
$$
\begin{align}
\sigma_y &= \pmatrix{0 & -i \\ i & 0}
\end{align}
$$
to the vectors
$$
\begin{align}
\ket {u} &= \pmatrix{1 \\ 0} \\
\ket {d} &= \pmatrix{0 \\ 1} \\
\ket {l} &= \pmatrix{1 \\ 0} \\
\ket {r} &= \pmatrix{1 \\ 0} \\
\end{align}
$$
<% tp.file.cursor(2) %>
