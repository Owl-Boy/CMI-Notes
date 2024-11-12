---
tags:
  - Note
---
202410172210

Tags : [[Automata Theory]]
# Myhill Nerode Theorem
---

>[!theorem]
>A language $L$ is a regular language iff there exists a right congruent equivalence relation $\sim$ of finite index $\Sigma^*$ that saturates $L$.

>[!attention] Notation
>- Index is the number of equivalence classes formed by a relation
>- An equivalence relation is said to saturate a language $L$ if any equivalence class is either disjoint from $L$ or is contained in $L$

***Proof:***
Given a regular language $L$, we can construct a [[Deterministic Finite State Automata|DFA]] $A = \langle Q, \Sigma, q_{0}, \delta, F \rangle$ for the language.

We now construct the following relation $\sim_{A}$ as follows:
- $x \sim_{A} y$ if and only if $\delta(q_{0}, x)=\delta(q_{0}, y)$.

This equivalence relation is a right congruent and it saturates $L$.

---
>[!theorem]
>Given a right congruent equivalence relation on $\Sigma^*$ which saturates $L$, once can construct an automata with as many states as there are equivalence classes.

Given an equivalence relation $\sim$, one can construct the following automata
- $\langle \Sigma^* / \sim,  \; \Sigma, \Delta, [\epsilon], \{ [x]: [x] \subseteq L \}\rangle$
which precisely accept $L$.

---
>[!definition]
>Given a language $L$, we can define the equivalence relation $\sim_{L}$ as follows:
>- We say $x \sim_{L} y$ iff forall $z\in \Sigma^*$ such that $xz \in L \iff yz \in L$
>- Another way to phrase it is $x \sim_{L} y$ iff $x^{-1}L = y^{-1}L$.

>[!theorem]
>$\sim_L$ is the coarsest right congruent equivalence relation.

Trivial from the definition of saturation.

---

>[!theorem] Corollary
>There is a unique minimal DFA for a regular language.

This is because any other automata with as many states as the minimal $DFA$ must construct an equivalence relation $\sim_{L}$ which makes the $DFA$ unique up to isomorphism.

---
# References
[[Right Congruent Equivalence Relation]]