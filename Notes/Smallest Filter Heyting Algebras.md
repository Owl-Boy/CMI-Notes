---
tags:
  - Example
---

202309121213

tags : [[Logic]]

#  Smallest Filter Heyting Algebras
---

**Lemma:** Let $A$ be the subset of a [[Heyting Algebra]] $H$. Then the smallest [[Filters in Heyting Algebras|filter]] which contains $A$ is 
$$
F=\{ a\in H\ :\ a\ge a_{1}\sqcap a_{2}\dots a_{k}\text{ where } a_{1},a_{2}\dots a_{k}\in A\}
$$

**Proof**:
$F$ contains $\overline a = a_{1}\sqcap\dots\sqcap a_{k}$, because for any $a, b\in F$ we have $a\sqcap b\in F$. Hence Any $a\ge\overline a\in F$.

Thus, if $\overline F$ is the smallest filter $\overline F\subseteq F$. But any Filter containing $A$ must be a superset of $F$ Hence $F$ is the smallest filter which contains $A$.

---
# Related
[[Heyting Algebra]]