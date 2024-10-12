---
tags:
  - Note
  - Incomplete
---
202409171009

Tags : [[Set Theory]]
# Cardinal Arithmetic
---
>[!note] Set Theory Used : $ZFC^-$

>[!definition]
>- $\kappa \oplus \lambda = | \{ 0 \} \times \kappa \cup \{  1 \} \times \lambda|$
>- $\kappa \otimes \lambda = |\kappa \times \lambda |$
>- $\kappa^\lambda = | \text{}^\lambda \kappa |$

We have that all the operations are monotonic, commutative, distributive

>[!quote] Gautham
>So here what you see is that cardinal arithmetic is *trivial*.

- For finite numbers, cardinal and ordinal arithmetic are the same.
- If one of the cardinals are infinite, then sum and product are max.

>[!theorem] 
>Fix $\lambda \geq \omega$, then for $2 \leq \kappa \leq 2^\lambda$, we have $\kappa^\lambda = 2^\lambda = |\mathcal P(\lambda)|$

***Proof***:
we have $2\leq \kappa \leq 2^\lambda$
We exponentiate everywhere and get 
$2^\lambda \leq \kappa^\lambda \leq (2^\lambda)^\lambda=2^{\lambda \otimes \lambda}=2^\lambda$

---
# References
[[Cofinality]]