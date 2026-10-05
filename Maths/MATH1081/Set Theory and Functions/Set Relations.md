## Membership
We can say that an object $a$ is an element of a set $\mathcal S$ with the symbol $\in$ like so: $x \in \mathcal S$. This reads as **$x$ is an element of $\mathcal S$**. 

You can also negate this statement with a line through the membership symbol $x \not \in \mathcal S$ which reads **$x$ is not an element of $\mathcal S$**.
## Subsets
A set $A$ is a **subset** of a set $B$ if and only if every element of $A$ is also an element of $B$. We denote this with $A \subseteq B$  which reads **$A$ is a subset of $B$**.

We can also say **$A$ is not a subset of $B$** with the notation $A \not \subseteq B$. 

We can then say that $\mathbb Z^+ \subseteq \mathbb N \subseteq \mathbb Z \subseteq \mathbb Q \subseteq \mathbb R \subseteq \mathbb C$.
## Equality
Now we have defined subsets we can also define equality between sets as:

Sets $A$ and $B$ are **equal** if and only if $A \subseteq B$ and $B \subseteq A$.
We can denote this as $A = B$.
## Proper subsets
We can also define a **proper subset** as

$A$ is a proper subset of $B$ if and only if $A \subseteq B$ and $A \not = B$.
We can denote this with $A \subset B$ or more explicitly $A \subsetneq B$, $A \subsetneqq B$ or $A\varsubsetneq B$ 
## Disjoint
The sets $A$ and $B$ are called **disjoint** if $A \cap B = \varnothing$.
## Pairwise Disjoint
The sets $A_1, A_2, A_3, \dots, A_k$ are **pairwise disjoint** if for all $i, j \le k$ with $i \not = j$ we have $A_i, A_j$ are disjoint.
## Partitioning
We say that the sets $A_1, A_2, A_3, \dots, A_k$ **partition** $B$ if $A_1, \dots, A_k$ are pairwise disjoint and $A_1\cup A_2 \cup A_3 \cup \dots \cup A_k = B$.
## Duality of set expressions
Given a set expression only involving sets, $\cup, \cap, \varnothing, \mathcal U$ and complements we can make the folowing substitutions to produce a new expression
$$
\begin{align}
\cup &\rightarrow \cap \\
\cap &\rightarrow \cup \\
\varnothing &\rightarrow \mathcal U \\
\mathcal U &\rightarrow \varnothing \\
\end{align}
$$
This new expression is called the **dual expression**.

### Duality principle
Any set statement involving only the above components are true if and only if it's dual is true!
