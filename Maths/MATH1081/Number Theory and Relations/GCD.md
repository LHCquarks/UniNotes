## GCD
The greatest common divisor of two integers $a, b$ when both $a, b$ are not $0$ is the natural number $d \in \mathbb N$ such that:
- $d \mid a$ and $d \mid b$
- for all $c \in \mathbb N$ that satisfy the first condition, $c \le d$
### Properties
- $\gcd(a, 1) = 1$ 
- $\gcd(a, 0) = |a|$
- $\gcd(a, \gcd(b, c)) = \gcd(\gcd(a, b), c)$
- $\gcd(ac, bc) = |c|\gcd(a, b)$
- if $a \mid bc$ and $\gcd(a, b) = 1$ then $a \mid c$
- if $a = qb + c$ then $\gcd (a, b) = \gcd(b, c)$
## LCM
The lowest common multiple (LCM) of two integers $a, b$ is the positive integer $d\in \mathbb Z^+$  such that:
- $a \mid d$ and $b \mid d$
- for all $c\in \mathbb N$ that satisfy the first condition, $d \mid c$
### Identity with GCD
It is known that $\text{lcm}(a, b)\gcd(a, b) = ab$ 
## Euclidean algorithm
### Division theorem
Given two numbers $a, b \in \mathbb Z$ with $b \not=0$, there exists two unique numbers $r, q \in \mathbb Z$ such that both
$$
\begin{align}
a &=qb + r \\
0 &\le r < |b|
\end{align}
$$
We will prove this for $a \ge 0, b > 0$ but this can fairly easily be extended encompass all of $\mathbb Z$.
We start with $r_0 = a, q_0 = 0$ and apply the following procedure:

 If $r_i \ge b$ then we can write:
 $$
\begin{align}
a &= q_i b + r_i \\
&= q_i b + (r_i - b) + b \\
&= (q_i + 1)b + (r_i - b)
\end{align}
$$
We can then define $q_{i+ 1} = q_i + 1, r_{i + 1} = r_i - b$ and thus we are back in a form of $a = q_{i + 1}b + r_{i + 1}$. We can then continue this process until $r_{n} < |b|$ in which case we will stop and our $q_n, r_n$ will satisfy both our conditions.
### Algorithm
The Euclidean algorithm is an algorithm that efficiently computes the $\gcd$ of two integers $a, b$. 

We start by using the divisibility theorem to get two numbers $q_0, r_0$ such that $a = q_0 b + r_0$. By the properties of $\gcd$ we know that $\gcd(a, b) = \gcd(b, r_0)$ and thus we have kicked the can down the road a bit. 
Importantly, because $0 \le r_0 < |b|$ we have decreased the size of the numbers we are working with and this process is infinity repeatable! Even further, whilst $r$ gets smaller and smaller it must always stay above or equal to $0$ and thus we eventually terminate:
$$
\begin{align}
a &= q_0b + r_0 \\
b &= q_1 r_0 + r_1 \\
r_0 &= q_2 r_1 + r_2 \\
&\ \ \vdots \\
r_{n-1} &= q_{n+1} r_n + 0
\end{align}
$$
At this point we get that $\gcd(a, b) = \gcd(b, r_0) = \dots = \gcd(r_n, 0) = r_n$ and thus we have found our $\gcd(a, b) = r_n$.
## Reverse Euclidean algorithm / Bezout's identity
Say that we have performed Euclid's algorithm and as a result have the equations:
$$
\begin{align}
a &= q_0 b + r_0 \\
b &= q_1 r_0 + r_1 \\
&\ \ \vdots \\
r_{n-3} &= q_{n-1} r_{n-2} + r_{n-1} \\
r_{n-2} &= q_n r_{n-1} + r_n \\
\end{align}
$$

we know that $r_n = \gcd(a, b)$ and so we will try and express this in terms of $a, b, x, y$ for some $x, y \in \mathbb Z$. To do this we rearrange all the equations to have the right most $r$ by itself:
$$
\begin{align}
r_0 &= a - q_0 b \\
r_1 &= b - q_1 r_0 \\
&\ \ \vdots \\
r_{n - 1} &= r_{n-3} - q_{n - 1} r_{n - 2} \\
r_n &= r_{n - 2} - q_n r_{n - 1}
\end{align}
$$
We can then head up the equations substituting in our $r$'s until we get to a point where we have some numbers $x, y$ such that $r_n = x a + y b$. Further, because we substituted expressions that comprise only of addition and multiplication $x, y$ must be integers.

The fact that we can write $\gcd(a, b) = xa + yb$ for some $x, y \in \mathbb Z$ is called **Bezout's identity**.
## Solving integer linear equations
Given integers $a,b,c\in \mathbb Z$  does the equation $c = ax + by$ have any solutions for integer $x, y$?

Suppose there exists $x, y\in \mathbb Z$ so that the above is true, then because $\gcd(a, b) \mid a$ and $\gcd(a, b) \mid b$ we have that $\gcd(a, b) \mid (ax + by)$ and thus $\gcd(a, b) \mid c$.

Now suppose that $\gcd(a, b) \mid c$, then $c = \gcd(a, b)k$ for some $k \in \mathbb Z$. By Bezout's identity we know that there exists some $x', y' \in \mathbb Z$  such that $\gcd(a, b) = ax' + by'$. Multiplying by $k$ we get $\gcd(a, b)k = c = a(x'k) + b(y'k)$ and thus $c = ax + by$ for $x = x'k, y = y'k$.

These statements work together to show given integers $a, b, c \in \mathbb Z$ the equation $c = ax +by$ as integer solutions if and only if $\gcd(a, b) \mid c$.

Further, to solve this equation we can use the reverse Euclidean algorithm to get our $x', y'$ and multiply by $k$ to get $x, y$.