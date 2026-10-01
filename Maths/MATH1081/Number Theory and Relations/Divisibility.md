## Definition
We say that $a$ **divides** $b$ if we can write $b = ak$ for some $k \in \mathbb Z$. We can also say:
- $a$ is a **divisor** of $b$
- $a$ is a **factor** of $b$
- $b$ is **divisible** by $a$
- $b$ is a **multiple** of $a$

We also write this fact as $a \mid b$ and we can write the inverse ("$a$ does not divide $b$") as $a \nmid b$.
## Some properties
- $a \mid a$ for all $a \in \mathbb Z$
- $a \mid b$ and $b \mid c$ implies $a \mid c$
- $a \mid b$ and $a \mid c$ implies $a \mid xb + yc$ for all $x, y \in \mathbb Z$
## Prime numbers
A **prime number** is any number $p \in \mathbb N$ such that $p > 1$ and the **only** positive divisors of $p$ are $1$ and $p$.
### Composite numbers
A composite number is any number $c\in \mathbb N$ such that $c > 1$ and $c$ is **not** a **prime**
### Infinitude of primes
There are infinitely many primes:

Suppose there was a finite set of primes $\mathbb P = \{p_1, p_2, \dots p_n\}$. Then we can construct a new integer $a = p_1p_2\dots p_n + 1$. This new number is not divisible by any of the primes in our set $\mathbb P$ therefor $a$ is a prime, a **contradiction**. Thus we conclude there are infinitely many primes

### Fundamental theorem of arithmetic
All natural numbers $n$ have a **unique** prime factorization. That is, we can write $n$ as:
$$
\begin{align}
n &= p_1^{\alpha_1} p_2^{\alpha_2}p_3^{\alpha_3}\dots
\end{align}
$$
where $p_k$ are primes and $\alpha_k$ are positive integers
## Common divisors
A common divisor of two integers $a, b$ is another integer $c$ such that $c \mid a$ and $c \mid b$ 
### Co-primes
Two integers $a, b$ are considered **co-prime** or **relatively prime** if their only common divisors are $\pm 1$ and we can notate this as $a \perp b$. 