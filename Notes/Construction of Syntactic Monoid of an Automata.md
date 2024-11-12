---
tags:
  - Note
---
202410272010

Tags : [[Algebraic Automata Theory]]
# Construction of Syntactic Monoid of an Automata
---
This is just a lazy construction of the monoid from the set of functions.

- Start by listing all the words ordered by length.
- We start with an empty set of functions, and each time we counter a word such that its function is not there in list, we add it and close the list under composition.
- If a "level" of words is completely contained in the list before we start checking it, then we stop the computation and return the list as the monoids

---
## Example
Consider the following automata
![[Syntactic Monoid Construction.excalidraw]]

This Automata Reads words that have both an $a$ and a $c$.
- We start with having, the identity function on the states for $\varepsilon$. 
- For $a$ we add the function that takes $L$ to $U$ and $D$ to $R$ and keeps everything else in place. We do it symmetrically for $c$. For be we get the identity function, so we equate it with $\varepsilon$.
- Then we can equate $aa$ with $a$, $ab$ with $b$, $bb$ with $\varepsilon$, $ba$ with $a$, $bc$ with $c$, $cb$ with $c$, $cc$ with $c$, then we add an entry for $ac$, and we can equate $ca$ with $ac$
- In the next step, we can simply equate all the words with existing ones. so we are done and have a multiplication table with $\varepsilon,a,c$ and $ac$.

---
# References
[[Monoids as Regular Languages#^a9668b|Syntactic Monoid]]