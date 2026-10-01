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
