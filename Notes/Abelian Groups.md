202304151104

Type : #Note
Tags : [[Algebra]]

---
# Abelian Groups
```ad-note
title:
Groups in which the binary operation is commutative are called _abelian groups_.
```

### Lemma 1:
```ad-note
title:
In a finite abelian group $G$, $\mathrm{ord}(b) | \max \{\mathrm{ord}(a) | a \in G\}$ for all $b \in G$.
```
##### Proof:
Let $a$ be the element with maximum order and let $b$ be any other element. 
If $\mathrm{ord}(b) \nmid \mathrm{ord}(a)$ then there is a prime $p$ such that $\mathrm{ord}(b) = p^jn$ and $\mathrm{ord}(a) = p ^{i}m$ such that $j > i$, and $m,n$ are coprime to $p$. Then $\mathrm{ord}(b^n a ^{p ^{i}}) = p ^{j} m > \mathrm{ord}(a)$. This is a contradiction. Hence $\mathrm{ord}(b) | \mathrm{ord}(a)$.

We are using the fact that if $x,y$ have coprime orders then their product has order equal to the product of their orders. 

---
# References
[[Groups]]
