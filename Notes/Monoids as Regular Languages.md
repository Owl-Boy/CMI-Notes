---
tags:
  - Note
---
202410172310

Tags : [[Algebraic Automata Theory]]
# Monoids as Regular Languages
---
Given a DFA $A = \langle Q, \Sigma, q_{0}, \delta, F\rangle$, one can construct the following finite monoid that recognizes the same language.

$$
\langle Q\to Q,\;\; ;\;\;, id_{Q}\rangle
$$
where $f ; g= g \circ f$, or the left associative $\circ$ and let $X=\{ f: f(q_{0}) \in F \}$. If $M$ is restricted to transitions that are actually possible to take in the automata, then that submonoid is called the *transition monoid* of the automata.

Given a monoid $\langle M, \cdot, 1\rangle$ with the monoid homomorphism $h$ from $\Sigma^*$ that recognizes a regular language, once can construct a DFA which accepts the same language as follows 
- $Q = M$
- $q_{0}=1$
- $\delta(q, a) = q \cdot h(a)$
- $F = X$

---
Given a finite state automata $A$, its canonical monoid would be the monoid construct my quotienting under the equivalence relation 
- $x \equiv_{A} y$ if $\delta_{x} = \delta_{y}$. 

This is isomorphic to the transition monoid.

Given a regular language $L$ the canonical monoid for $L$ would be for similarly by quotienting under the congruence relation $\equiv_{L}$ as defined as 
- $x \equiv_{L} y$ if $\forall w\ z, wxz \in L \iff w y z \in L$.

This is isomorphic to the transition monoid of the minimal DFA and is called the *syntactic monoid* of the language. ^a9668b

---
# References
[[Monoids as Languages]]