---
tags:
  - Note
---
202403241003

Tags : [[Games on Graphs]]
# Winning Strategy for Büchi Games
---
## Elster
>[!Theorem] Lemma
>***Elster*** has a winning strategy from $\text{attr}_{E}(A, Z(n))$ if $Z(n) = Z(n+1)$

- Case 1 : $v\in Z(n)$
	- then $v\in Z(n+1)$, by the definition of $Z$ we have $v\in \text{pre}_{E}(\text{attr}_{E}(A, Z_{n}))$, then we can continue for case 2
	- So we take the non empty path to an element in $Z(n)$ and repeat the stategey
- Case 2 : $v \notin Z(n)$
	- In this case we can always move to some node in $Z_n$ as $v\in \text{Attr}_{E}(A, Z(n))$
	- So we get to $Z(n)$ and use the strategy in case 1.

---
## Adler
>[!theorem] Lemma
>***Adler*** has a winning strategy from $V\setminus \text{Attr}_{E}(A, Z(n))$

We notice that $A_A$ is the complement of an attractor set. So ***Adler*** will use the trapping strategy to keep the game away from $A_E$ using the strategy discussed in [[Winning Arena for Reachability Games]], until the play Visits a vertex in $X$.

For this position we have $A_A = V \setminus X(n)$. Let $i$ be the largest index such that $v\in X(i)$ but $v\notin X(i+1)$, so Alder can keep the game out of $\text{Attr}_{E}(Z(i+1))$. 

Here ***Alder*** uses trapping strategy to keep the game out of $Attr_E(Z(i+1))$ till the game reaches a point $v$ in $G$. We have that $v\notin Y(i)$ so after a move, we can go outside $X_i$, hence we go outside $\text{Attr}_E(Z(i))$ and ***Adler*** uses trapping strategy again.

Hence the game will remain out of $X(j)$ forall $j>i$. Therefor the next $v\in G$ that is visited will be in $X(k)$ where $k$ is less than $i$, but the same idea is used. This process cannot go on indefinitely hence eventually the game will remain out of $X_1$ which contains $G$.

At some point we will reach $X(0)\setminus X(1)$ which is the set of points from where ***Adler*** can force the game to only those vertices that are not good states, or are dead ends for ***Elster***. Hence ***Adler*** has a winning strategy.

Modifying the algorithm in the following manner makes it easier to see why ***Adler*** will have a winning strategy.

```
Let Z(0) = V
until Z(i) stabilizes:
  X(i) = Attr_E(A, Z(i))
  Y(i) = pre_E(X(i))
  Z(i+1) = Y(i) /\ Z(i)
end until at n
return Attr_E(A, Z(n))
```

---
# References
[[Winning Arena for Büchi Games]]
[[Winning Arena for Reachability Games]]
[[Winning Strategy for Reachability Games]]