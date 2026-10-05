## The Modulo operator
Often times when talking about divisibility we are only interested in the remainder $r$ (from $a = qb + r$) and thus we have a special notation for it:

The modulo operator $\text{mod}$ returns the canonical remainder when one integer is divided by another (ie it returns the $r$). We write $a \text{ mod } b = r$  which reads as "$a$ modulo $b$ equals $r$". 
## Equivalence classes and congruence
Given numbers $b, c \in \mathbb Z$ the equation $x \text{ mod } b = c$ has infinitely many solutions but these solutions all share the fact that they solve the above equation. Because they all share this same property we say the belong to the same **equivalence class**. 

Given $x, y$ that both solve the above equation we can write $x \equiv y \pmod{b}$  which reads "$x$ is **congruent** to $y$ under $\text{mod } b$".
## Properties of modular arithmetic
- If $a \equiv b \pmod{m}$ and $k \in \mathbb Z^+$ satisfies $k \mid m$ then $a \equiv b \pmod{k}$
- If $a \equiv b \pmod{m}$ and $c \equiv d \pmod{m}$ then $a + c \equiv b + d \pmod{m}$
- If $a \equiv b \pmod{m}$ and $c \equiv d \pmod{m}$ then $ac \equiv bd \pmod{m}$
- $a\equiv b \pmod{m} \iff ak \equiv bk \pmod{mk}$ for all $k \in \mathbb Z^+$
- If $ak \equiv bk \pmod{m}$ for some $k \in \mathbb Z$ and $\gcd(k, m) = 1$ then $a \equiv b \pmod{m}$
- If $a \equiv b \pmod{m}$ then $a^k \equiv b^k \pmod{m}$ for all $k \in \mathbb Z^+$
- 