---
tags:
  - Note
  - Incomplete
---
202410271910

Tags : [[Algebraic Automata Theory]]
# Monoids as Idempotent Commutative Langauges
---
Given a monoid if $a\cdot b = b\cdot a$ for all $a, b\in M$, then we say that $M$ is commutative. If $a\cdot a = a$ forall $a\in M$ we say that $M$ is idempotent.

Any Language that can be accepted by a commutative(or idempotent) monoid is called a commutative(or idempotent) language. 

Given a language of the following type: $L \subseteq \Sigma^* = A^*$ for some $A\subseteq \Sigma$. Given a commutative idempotent language, there is a very simple construction of a monoid that recognizes it.

$$
M := \langle \{ 0, 1, A \}, \times, 1 \rangle
$$
- Here the set has just 3 elements
- the multiplication operator is idempotent on $A$ with $0$ being the co-unit and $1$ being the unit element.
- The morphism $h: \langle \Sigma^*, \cdot,\epsilon\rangle \to M$ sends $a$ to $A$ if $a\in A$, otherwise it sends $a$ to $0$
- The subset that recognizes $L$ is $\{ A, 1 \}$


Since a surjective homomorphism takes idempotent commutative monoids to idempotent commutative monoids, idempotent commutative languages are closed under boolean operations and division.

This also gives a simple construction for idempotent commutative languages from the previous construction as all such languages are boolean combinations of previous languages.

---
# References
[[Construction of Syntactic Monoid of an Automata]]