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
### The empty set
There is a special set called the empty set defined as $\emptyset = \{\} = \varnothing$. This set has no elements.
## Sets within sets
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
## The universal set
When working with sets it is often usefull to talk about a set containing every possible object within the context. This set is known as the **universal set** and is often denoted as $\mathcal U$ or $U$.

Further, all sets are subsets of $\mathcal U$.

Importantly the "all possible objects" can not include the sets containing these object as we will run into Russell's paradox.

If we are working with intervals of the real number line then we could define $\mathcal U = \mathbb R$ but if we are working solely with integers then we can define $\mathcal U = \mathbb Z$.
## Tuples
A tuple is a **finite**, **ordered** collection of objects. It is just like a set but order matters and the elements do not have to be unique.

Tuples are writen with rounded brackets like so: $(1, 2, 3, 4) \not = (1, 2, 4, 3)$.

A tuple with size $n$ can also be refered to as an n-tuple and in the special case where $n = 2$ it can also be refered to as an **ordered pair**.