---
tags:
  - Note
  - Incomplete
---
202311182111

Tags : [[Logic]], [[Timed Automata]]
# Hardness of LTL Model Checking using Timed Automata
---
>[!note] Theorem
>Over finite timed words, the almost-sure and large [[Linear Temporal Logic|LTL]] model-checking problem over non-blocking timed automata are $\text{PSPACE-}$Complete
>

Because of the [[Correspondence of Topological and Probabilistic Semantics for LTL]], we have that the above two models are equivalent. And $\text{PSPACE}$-Hardness comes directly from [[PSPACE-Hardness of LTL Model Checking]].

## $\text{PSPACE}$ Algorithm for model checking 
- We first construct the region automaton $\text{R}(\mathcal A)$ for the automaton.
- Then we colour each edge in the following manner.
	- We colour it *red* whenever $\mu_s(I(s, e))=0$ for some $s\in q$
	- Otherwise we colour it *blue*
- Now to decide whether $\mathcal A,s\mid\!\not\approx \varphi$, it is sufficient to guess a path in $\text{R}(\mathcal A)$ that does not contain any red edges. This can be done in $\text{PSPACE}$.


---
# References
