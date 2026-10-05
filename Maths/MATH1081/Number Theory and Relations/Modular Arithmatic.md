## The Modulo operator
Often times when talking about divisibility we are only interested in the remainder $r$ (from $a = qb + r$) and thus we have a special notation for it:

The modulo operator $\text{mod}$ returns the canonical remainder when one integer is divided by another (ie it returns the $r$). We write $a \mod b = r$  which reads as "$a$ modulo $b$ equals $r$". 
## Equivalence classes and congruence
Given numbers $b, c \in \mathbb Z$ the equation $x \mod b = c$ has infinitely many solutions but these solutions all share the fact that they solve the above equation. Because they all share this same property we say the belong to the same **equivalence class**. 

Given $x, y$ that both solve the above equation we can write $x \equiv y \pmod{b}$  which reads "$x$ is **congruent** to $y$ under $\mod b$".
## Properties of modular arithmetic
- If $a \equiv b \pmod{m}$ and $k \in \mathbb Z^+$ satisfies $k \mid m$ then $a \equiv b \pmod{k}$
- If $a \equiv b \pmod{m}$ and $c \equiv d \pmod{m}$ then $a + c \equiv b + d \pmod{m}$
- If $a \equiv b \pmod{m}$ and $c \equiv d \pmod{m}$ then $ac \equiv bd \pmod{m}$
- $a\equiv b \pmod{m} \iff ak \equiv bk \pmod{mk}$ for all $k \in \mathbb Z^+$
- If $ak \equiv bk \pmod{m}$ for some $k \in \mathbb Z$ and $\gcd(k, m) = 1$ then $a \equiv b \pmod{m}$
- If $a \equiv b \pmod{m}$ then $a^k \equiv b^k \pmod{m}$ for all $k \in \mathbb Z^+$
## Fermat's little theorem
Fermat showed that for prime $p$ and integer $a$, as long as $p \not\mid a$ then 
$$
\begin{align}
a^{p - 1} \equiv 1 \pmod{p}
\end{align}
$$
We do not prove this in this course but we can use it to solve problems like:

Simplify $99^{100} \pmod{101}$. 
$101$ is a prime and $99 \not \mid 101$ so FLT implies $99^{100} \equiv 1 \pmod{101}$

Simplify $99^{909} \pmod{101}$.
$$
\begin{align}
99^{909}&\equiv \left(99^{101}\right)^9 \pmod{101} \\
&\equiv \left(99^{100} 99\right)^9 \pmod{101} \\
&\equiv \left(99^{100}\right)^9 99^9 \pmod{101} \\
&\equiv \left(1\right)^9 99^9 \pmod{101} \\
&\equiv 99^9 \pmod{101} \\
&\equiv (-2)^9 \pmod{101} \\
&\equiv -512 \pmod{101} \\
&\equiv 94 \pmod{101} \\
\end{align}
$$
## Solving linear modular equations
Say we have the equation $ax \equiv c \pmod{m}$ for known numbers $a, c, m \in \mathbb Z$ and variable $x \in \mathbb Z$. 

To solve this we will relate it back to the tools we used for normal integer equations and use Bezout's identity:
$$
\begin{align}
ax &\equiv c \pmod{m} \\
ax + my&\equiv c \\
\end{align}
$$
We can then solve the non-modular equation $ax + my = c$ through prior techniques and Bezout's identity and the $x$ values then become solutions for the first equation.
## Multiplicative inverses
The multiplicative inverse of an integer $x$ under $\mod{m}$ (if it exists) is a number $y$ such that $xy\equiv 1\pmod{m}$. An example is $5$ is the **multiplicative inverse** of $3$ under $\mod{7}$ as $3 \times 5 \equiv 15 \equiv 1 \pmod{7}$.

If the inverse of $x$ exists we can write it as $x^{-1}$ and use it to easily solve our linear equations.
$$
\begin{align}
3 x &\equiv 4 &\pmod{7} \\
x &\equiv 3^{-1}\times 4 &\pmod{7} \\
x &\equiv 5\times 4 &\pmod{7} \\
x &\equiv 20 &\pmod{7} \\
x &\equiv 6 &\pmod{7} \\
x &= 6 + 7y
\end{align}
$$
for all $y \in \mathbb Z$.
