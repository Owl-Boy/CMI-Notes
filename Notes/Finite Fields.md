202304151104

Type : #Note
Tags : [[Algebra]]

---
# Finite Fields
### Lemma 1:
```ad-note
title:
If $F$ is a finite field, the group $F ^{\times}$ is cyclic.
```
##### Proof:
We use Lemma 1 from [[Abelian Groups]].
Let $|F| = q$.
Let $m$ be the maximum order of elements of $F ^{\times}$. Since the order of every element divides $m$, we get that $x ^{m} = 1$ for all $x \in F ^{\times}$. So the polynomial $X ^{m}-1$ has all the $q-1$ elements of $F ^{\times}$ as roots.
But since the number of roots of a polynomial is bounded above by its degree, we get that $q-1 \le m$ 
But $m | q-1$ by lagrange's theorem. This gives $m = q-1$ and $F ^{\times}$ is cyclic.

---
# References
[[Abelian Groups]]