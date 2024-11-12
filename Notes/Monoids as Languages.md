---
tags:
  - Note
---
202410172310

Tags : [[Algebraic Automata Theory]]
# Monoids as Regular Languages
---
Right congruence classes are a nice way of categorizing languages which are equivalent to automata.

We now construct a stronger congruence relation as follows
- $x \equiv y \implies \forall w\ z, wxz \equiv wyz$ or, equivalently
- $x \equiv y \land x' \equiv y' \implies x \cdot x' \equiv y \cdot y'$

Given the above equivalence relation we can construct the following monoid
$$
\langle \Sigma /\! \equiv, \cdot, [\epsilon] \rangle
$$

>[!definition] 
>If there exists a [[Monoid Homomorphisms]] $h: \langle\Sigma^*, \cdot, \epsilon\rangle \to \langle M, *, 1\rangle$ such that there exits a subset $X \subset M$ such that $h^{-1}(X)=L$ then we say that $M$ *recognizes* $L$.

---
# References
[[Monoids as Regular Languages]]