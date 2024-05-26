---
tags:
  - Note
  - Incomplete
---
202402121102

Tags : [[Linear Programming]], [[Combinatorial Optimisation]]
# Farkas' Lemma
---

> [!question] Exactly one of the two systems has a solution.
> 1. $Ax=b$, $x\geq 0$
> 2. $y^{T}A\geq 0$, $y^{T}b<0$.

$A\in\mathbb{R}^{m\times n}$, $b\in\mathbb{R}^{m}$, $x \in\mathbb{R}^{n}$, $y\in\mathbb{R}^{m}$.

(1) has a solution $\implies$ (2) doesn't have a solution.
Let $\hat{x}$ be a solution to (1), $\hat{x}\geq 0$, $A \hat{x}=b$.
For any $y$, $y^{T}A\hat{x}=y^{T}b$.
$y^{T}A\geq 0, \hat{x}\geq 0\implies y^{T}b\geq 0$.
(2) has no solution.

## Systems
---
1. $Ax\leq b$
2. $y\geq 0$, $y^{T}A=0$, $y^{T}b<0$.

If (1) has a solution $\hat{x}$, then $A\hat{x}\leq b$, $y^{T}A\hat{x}\leq y^{T}b$ for $y\geq 0$.
So $0\leq y^{T}b$, which contradicts (2).



---
# References
