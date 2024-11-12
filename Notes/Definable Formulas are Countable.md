---
tags:
  - Note
  - Incomplete
---
202411021511

Tags : [[Set Theory]]
# Definable Formulas are Countable
---
We define the following function that enumerates all definable formulas
>[!Definition]
>By recursion on $m\in \omega, \text{En}(m, A, n)$ is defined (for all $n$ simultaneously) by the following clauses.
>1. If $m=2^i 3^j$ and $i,j < n$ then $\text{En}(m, A, n)=\text{Diag}_{\in}(A, n , i, j)$
>1. If $m=2^i 3^j 5$ and $i,j < n$ then $\text{En}(m, A, n)=\text{Diag}_{=}(A, n , i, j)$
>1. If $m=2^i 3^j 5^2$, then $\text{En}(m, A, n)=A^n\setminus \text{En}(i, A, n)$
>1. If $m=2^i 3^j 5^3$ then $\text{En}(m, A, n)=\text{En}(i,A,n) \cap \text{En}(j, A, n)$
>1. If $m=2^i 3^j 5^4$ then $\text{En}(m, A, n)= \text{Proj}(A,\text{En}(i,A, n+1), n)$
>2. Otherwise $\text{En}(m, A, n)=\emptyset$

Along with the lemma $\text{Df}(A, n) = \{ \text{En}(m, A, n): m \in \omega \}$ we have that the formulas are countable.

>[!definition] Elementary Equivalence
>We say that $A \equiv B$ iff 
>$$
>\forall m(\text{En}(m, A, 0)=\text{En}(m, B, 0))
>$$
>That is, $A, B$ agree on all sentences.

---
# References
