## Sets
A **set** is a well-defined, unordered collection of distinct objects. The objects contained in a set are called its **elements**

Sets are denoted with a pair of curly brackets arround the elements of a set as such:
A set $\mathcal S$ continaing the elements $1, 3, 5$ can be written as
$$
\begin{align}
\mathcal S = \{1, 3, 5\}
\end{align}
$$

Since sets are **unordered** we have that $\{3, 1, 2\} = \{1, 2, 3\}$.

Since elements of a set are distinct repeted elements are ignored: $\{1, 2, 2, 3, 3, 3\} = \{1, 2, 3\}$

Further, we can write our sets discriptivly instead of listing all elements like so:
- $\{\text{even numbers between } 1 \text{ and } 9\} = \{2, 4, 6, 8\}$   
- $\{\text{Letters in BANANA}\} = \{B, A, N\}$
## Membership
We can say that an object $a$ is an element of a set $\mathcal S$ with the symbol $\in$ like so: $x \in \mathcal S$. This reads as **$x$ is an element of $\mathcal S$**. 

You can also negate this statement with a line through the membership symbol $x \not \in \mathcal S$ which reads **$x$ is not an element of $\mathcal S$**.
## Conditional definitions
When defining a set we can also apply conditions to our elements with a coline ($:$) or a vertical bar ($|$) where on the left is the elements and on the right is the condition. 

As an example we can express the set of all even numbers like so: $\mathcal S = \{x\in \mathbb R | x \text{ is even}\}$. 
This can read as **all real numbers $x$ such that $x$ is even**.
## Common sets
- The set of all **natural numbers**: $\mathbb N = \{0, 1, 2, 3, \dots\}$. Note in this course $0 \in \mathbb N$
- The set of all **integers**: $\mathbb Z = \{\dots, -3, -2, -1, 0, 1, 2, 3, \dots\}$
- The set of all **positive integers**: $\mathbb Z^+ = \{1, 2, 3, \dots\}$
- The set of all **rational numbers**: $\mathbb Q = \left\{\frac{p}{q}: p, q \in \mathbb Z, q \not = 0\right\} = \left\{\frac{p}{q}: p\in \mathbb Z, q\in \mathbb Z^+\right\}$ 
- The set of all **real numbers**: $\mathbb R = \{\text{the closure of } \mathbb Q\}$ 
- The set of all **complex number**: $\{a + bi: a, b \in \mathbb R, i^2 = -1\}$
## The empty set
There is a special set called the empty set defined as $\emptyset = \{\} = \varnothing$. This set has no elements.
## Cardinality / size of a set
We define the **cardinality** or **size** of a set $\mathcal S$ as the number of elements in $\mathcal S$. We can denote this with $|\varnothing| = 0$ 
## Sets within Sets
Because sets can contian any object sets can also contain sets eg, $\mathcal S = \{1, 2, \{3, 4\}\}$ is a valid set with the following properties:
$$
\begin{align}
1 &\in \mathcal S \\
3 &\not \in \mathcal S \\
\{3, 4\} &\in \mathcal S \\
|\mathcal S| &= 3
\end{align}
$$
### Russell's paradox
Consider the set $\mathcal S = \{\text{sets which are not elements of themselves}\}$. Now consider if $\mathcal S$ is an element of itself:
- if $\mathcal S \in \mathcal S$ then by definition we get that $\mathcal S \not \in \mathcal S$. This can not be true
- if $\mathcal S \not \in \mathcal S$ then by definition we get that $\mathcal S \in \mathcal S$. This also can not be true
Thereby $\mathcal S$ is both not an element of itself an is an element of itself which is a contradiction.

The issue is that $\mathcal S$ is not a well defined and thus violates our definition of sets
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
## Power sets
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
