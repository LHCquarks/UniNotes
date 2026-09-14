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
