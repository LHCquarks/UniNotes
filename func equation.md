$$
\begin{align}
f(f(x)) + xf(x) &= 1 \\ \\
\text{let } x = 0 &\\
f(f(0)) + 0 &= 1 \\
f(f(0)) &= 1 \\ \\
\text{let } x = f(0) & \\
f(f(f(0))) + f(0)f(f(0)) &= 1 \\
f(1) + f(0) &= 1 \\
f(0) &= 1 - f(1) \\ \\
\text{let } x = 1& \\
f(f(1)) + f(1) &= 1 \\
f(1) &= 1- f(f(1)) \\
\implies
f(0) &= f(f(1)) \\
f(0) &= f(1- f(0)) \\\\
f(0) &= 1 - f(1) \\
f(f(0)) &= f(1- f(1)) \\
1 &= f(1 - f(1)) \\ \\
\text{let } g(x) = f(1 - x) &\\
\implies g(0) &= f(1) \\
g(1) &= f(0) \\\\
\text{let: }& \\
f(0) &= a \\
f(1) &= b \\
\implies \\
a &= 1 - b \\
a &= f(1 - a) \\
1 &= f(1 - b) \\

\end{align}
$$
<% tp.file.cursor(2) %>