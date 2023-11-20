---
tags:
  - Note
  - Incomplete
---
202311051511

Tags : [[Programming Languages]], [[Lambda Calculus]]
# let(rec)-expressions to Ordinary Lambda Calculus
---
We categorise these expressions into multiple categories and build a multi-step conversion to get from complicated *Let(rec)-expressions* to ordinary Lambda Calculus.

The procedure is captured by the diagram

![[Pasted image 20231107143320.png]] ^aa141c

- We first do [[Dependency analysis for letrec expressions]].
- We then transform general *let(rec)* expressions to [[Irrefutable let(rec)]] expressions by [[Conformality Transformation on let(rec) expressions]]
- We then convert [[Irrefutable let(rec)s to Simple let(rec)s]]
- We then convert [[letrec-expressions to Irrefurtable let-expressions]]
- And we finally convert all [[Simple let expressions to Ordinary Lambda Calculus]]

---
# References
[[Converting Enriched Lambda Calculus to Ordinary Lambda Calculus]]