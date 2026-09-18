## Cardinality / size of a set
We define the **cardinality** or **size** of a set $\mathcal S$ as the number of elements in $\mathcal S$. We can denote this with $|\varnothing| = 0$ 
## Power Sets
The **power set** of a set $\mathcal S$ is the set containing all subsets of $\mathcal S$:
$$
\begin{align}
\mathcal P(\mathcal S) = \{x: x\subseteq \mathcal S\}
\end{align}
$$
For instance $\mathcal P(\{1, 2, 3\}) = \{\{\}, \{1\}, \{2\}, \{3\}, \{1, 2\}, \{1, 3\}, \{2, 3\}, \{1, 2, 3\}\}$ 
### Cardinality of $\mathcal P(\mathcal S)$
Suppose that $\mathcal S$ has $n$ elements.
Order all the possible subsets sets by their cardinality. We can then determine the number of these sets using combinatorics:
$$
\begin{align}
|x| = 0 &\implies \pmatrix{n \\ 0} \text{ sets} \\
|x| = 1 &\implies \pmatrix{n \\ 1} \text{ sets} \\
|x| = 2 &\implies \pmatrix{n \\ 2} \text{ sets} \\
&\vdots
\end{align}
$$
Thus the total number of sets in our power set is:
$$
\begin{align}
\sum_{j = 0}^n \pmatrix{n \\ j} &= 2^n
\end{align}
$$
by pascall's triangle. Thus $|\mathcal P(\mathcal S)| = 2^{|\mathcal S|}$.
## Union
The **Union** of two sets $A, B$ is defined as a new set $C$ such that
$$
\begin{align}
C = \{x \in \mathcal U| x \in A \text{ or }x \in B\}
\end{align}
$$
We write this as $C = A \cup B$ which reads as **C equal A union B**.
## Intersection
The **Intersection** of two sets $A, B$ is defined as a new set $C$ such that
$$
\begin{align}
C = \{x\in \mathcal U | x \in A \text{ and }x \in B\}
\end{align}
$$
We write this as $C = A \cap B$  which reads as **C equals A intersect B**.
## Complement
The **Complement** of a set $A$ is definied as a new set $B$ such that
$$
\begin{align}
B = \{x\in \mathcal U | x \not \in A\}
\end{align}
$$
We write this as $B = \bar A$ or $B = A^c$ which reads as **B equals the complement of A**.
## Set diference
The diference of two sets $A, B$ is a set $C$ such that
$$
\begin{align}
C = \{x \in A| x \not \in B\}
\end{align}
$$
We write this as $C = A - B$ or $C = A \backslash B$  which reads **C is A excluding B**.
## Symetric diference
The symetric diference of two sets $A, B$ is a set $C$ such that
$$
\begin{align}
C &= \left(A \cup B\right) \backslash \left(A \cap B\right) \\
&= (A - B) \cup (B - A)
\end{align}
$$
We write this as $C = A \ominus B$, $C = A \oplus B$ and $C = A \triangle B$ which reads **C is the symetric diference of A and B** or for $A \ominus B$ we can say **A sym-dif B**.
