16-11-2022 09:27 am

Type : #Note
Tags : [[Algebra]]

```ad-note
title: Theorem
$\exists$ a finite field of order $q = p^n$, and all fields of order $q$ are isomorphic. 
```
### Proof:
- Let $K$ be the field of roots of the polynomial $x^q-x$ over $\mathbb{F}_p$. This shows existence.
- For uniqueness, let $K,K'$ be two fields of order $q$, they are vector spaces over $\mathbb{F}_p$. Elements of $K,K'$ satisfy $x^q-x$ (why? because the non zero elements of $K'$ forms a group of order $q-1$, hence $x^{q-1}=1 \ \forall \ x \in K'$). Hence they are isomorphic.

---
```ad-note
title: Theorem
A field of order $p^r$ contains a field of order $p^k$ iff $k | r$
```

```ad-note
title: Lemma
Let $X,Y$ be variables and $q = p^r$, then 
$$(X+Y)^q = X^q + Y^q$$
```
### Proof:
- Binomial expansion

---
```ad-note
title:Lemma 
Let $K$ be a field and let $L = \{ \alpha \in K \ | \ \alpha^q-\alpha = 0\}$
Then $L$ is a subfield of $K$.
```
### Proof:
- Just check closure under addition, multiplication, and inverses.

```ad-note
title: Claim
$-1$ is a root of $x^q-x$.
```
### Proof:
- $q$ is odd, if $p$ is odd.
- if $p = 2$, then $(-1)^q+1 = 1 + 1 = 2 = 0 \ ( \text{mod} \ 2)$
--- 
### Proof of Theorem:
- Let $q = p^r, q' = p^k$
- Then, $[\mathbb{F}_q : \mathbb{F}_p] = r$ and $[\mathbb{F}_{q'} : \mathbb{F}_p] = k$
- If $\mathbb{F}_q$ contains an isomorphic copy of $\mathbb{F}_{q'}$, then $k | r$.
- Conversely, if $k | r$, we need to show that $\mathbb{F}_{q'}$ is a subfield of $\mathbb{F}_q$.
- By our lemma, it is enough to show that elements of $\mathbb{F}_{q'}$ satisfy $x^q-x$.
- enough to show that $x^{q'}-x | x^q-x$.


---

```ad-note
title: Primitive Element
Let $K/F$ be a field extension. An element $\alpha \in K$ is called a primitive element if $K = F(\alpha)$
```

```ad-note
title: Primitive Element Theorem
1) Let $K/F$ be a finite extension then there is a primitive element for K/F iff the number of intermediate fields is finite.
2) Let $K/F$ be a finite and separable extension, then $K$ has a primitive element.
```

### Proof:
- If $K/F$ is a finite field, then $K^{\times}$ is a cyclic group.


---
# References:
[[Algebraic Extension]]
[[Extension Field]]
[[Fields]]