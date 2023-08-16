202308161508

Type : #Note
Tags : [[Logic]]

---
# Lattice
A lattice is a poset such that any two pairs of elements hvae a least upper bound and a greatest lower bound
$$
\begin{matrix}a\le a\sqcup b & &a\sqcap b\le a \\b\le a\sqcup b && a\sqcap b\le b \\ c\le a,c\le b\implies c\le a\sqcap b && a\le c, b\le c\implies a\sqcup b\le c \end{matrix}
$$

```ad-info
title: distributive lattices
A lattice which satisfies
$(a\sqcap b)\sqcup c=(a\sqcup c)\sqcap(b\sqcup c)$
$(a\sqcup b)\sqcap c=(a\sqcap c)\sqcup(b\sqcap c)$
is called a **Distributive Lattice**
```

If a lattice has $0$ and $1$, $b$ is said to be a _complement_ of $a$ if $a\sqcap b=0$ and $a\sqcup b=1$

![[Boolean Algebra#^89f0ee]]

**Heyting Algebra:**
![[Heyting Algebra#^20491c]]

---
# References
