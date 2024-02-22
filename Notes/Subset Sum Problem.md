---
tags:
  - Note
  - Incomplete
---
202401121101

Tags : [[Complexity Theory]]
# Subset Sum Problem
---
Given a set of positive integers $\{ w_{1},\dots w_{n} \}$ and an integer $W$, find a subset of the set such that they sum up to $W$.
We can use dynamic programming to solve this. But the hardness of this problem lies in the fact that the input is given in binary (or anything that's not unary). The size of the input thus becomes $O\left( \sum \log w_{i}+\log W \right)$, and poly in that is the challenge.

## Reduction from 3-SAT to Subset Sum
---
Assign two numbers $a_{i}=10^{m+i}+\sum\limits_{x_{i}\in C_{j}}10^{j}$, and $b_{i}=10^{m+i}+\sum\limits_{\bar{x_{i}}\in C_{j}}10^{j}$, for each variable $x_{i}$. Now, for every truth assignment in $\{ 0,1 \}^{n}$, consider the sum $\sum\limits_{i=1}^{n}(x_{i}a_{i}+(1-x_{i})b_{i})$. This has length $n+m$ digits, where the first $n$ digits will be all $1$'s, and the rest will contain a $0$ if the clause is not satisfied and $1,2$ or $3$ otherwise. We add some padding variables $c_{j},d_{j}$ so that the $1$'s and $2$'s can be made $3$'s, but the $0$'s can't.
So the set of numbers is $\{a_{1},\dots, a_{n},b_{1},\dots, b_{n},c_{1},\dots, c_{m},d_{1},\dots, d_{m}\}$, and $W=\sum\limits_{i=1}^{n}10^{m+i}+\sum\limits_{j=1}^{m}3.10^{j}$.


---
# References
[[Web of Reductions]]