---
tags:
  - Note
---
202411051911

Tags : [[Algebraic Automata Theory]], [[Monoid Theory]]
# Finite Monoids and idempotent elements in big words
---
Given a finite monoid/semigroup $M$ with $n$ elements, $a_{1},a_{2},a_{3}\dots a_{n}$.

Let $a_{1}\dots a_{l}$ be a word, we construct the following graph on the word.
- let $V= [1..l]$
- let the colour of the edge from vertex $x$ to vertex $y$ be $a_{x},a_{x+1}\dots a_{y}$
- [[Ramsay's Theorem]] gives us a monochromatic clique $b_{1}\dots b_{k}$. 
- Elements of the clique cut of the word into tiny parts, each of those tiny parts will correspond to an idempotent element $e$ because, each part multiplies to give the same colour, and multiple parts combine together to also give the same colour since the graph is complete and monochromatic.

This theorem seems very much like *Pumping Lemma* and is if we want to talk about it for monoids as languages, the statement is independent of the alphabet. Infact, if one is given the chunks of words that must be multiplied together, one can still to the previous construction by just taking the homomorphism from $(\Sigma^*)^* \to M$ instead of $\Sigma^* \to M$.

For infinite words, this breakup can be done in a following way.

Similarly construct an infinite graph and get the infinite monochromatic subgraph. And start from its start dividing it into chunks like the previous construction, this leads to the word break in the following way 
$$
\underbrace{a_{1},\dots a_n}_{s}
\underbrace{b_{1},\dots b_{m}}_{e}
\underbrace{c_{1},\dots c_{o}}_{e}\cdots
$$
such that $s\cdot e = s$ and $e\cdot e = e$.

---
# References
[[Ramsay's Theorem]]
[[Every Finite Semi Group has an idempotent element]]