---
tags:
  - Example
---
202309121209

Tags : [[Logic]]

---
# Extension of Proper Filter to Prime Filter in Heyting Algebras

**Lemma:**
Let $F$ be a [[Filters in Heyting Algebras|proper filter]] in $\mathcal H$ and let $a\notin F$. Then there exists a prime filter $G$ such that $F\subseteq G$ and $a\notin G$.

**Proof:**
Consider $\mathcal F$ to be the set of filters that do not contain $a$ but contain $F$ with inclusion as the partial order.

Here the union of every chain is also in $\mathcal F$ hence all chains have upper bounds. By Zorn's Lemma, There is a Maximal element $G$.

We need to prove that $G$ is prime.

Consider $G_{y}=\{x\ :\ x\ge g\sqcap y\}$ for some $g\in G$(Pick $y$ and $g$ and find the smallest filter which contains both). If $c\sqcup b\in G$. Then consider $G_{c}$ and $G_{b}$.

If both of them contain $a$ Then there are $g_{1},g_{2}\in G$ such that $g_{1}\sqcap b\le a$ and $g_{2}\sqcap c\le a$. since $g_{1}, g_{2}, b\sqcup c\in G$ we have $(g_{1}\sqcap g_{2})\sqcap (b\sqcup c)\in G$.

We also have $a=a\sqcup a\ge (g_{1}\sqcap g_{2}\sqcap b)\sqcup(g_{1}\sqcap g_{2}\sqcap c) = (g_{1}\sqcap g_{2})\sqcap(b\sqcup c)\in G$ which is a contradiction.

Thus one of $G_{b}$ and $G_{c}\in\mathcal F$ and by primality of $G$ we have either $b, c\in G$ thus $G$ is prime.


---
# References
