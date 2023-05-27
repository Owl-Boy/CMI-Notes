202304161004

Type : #Note
Tags : [[Algebra]]

---
# Galois Correspondence
```ad-info
title: Idea
Given a field extension $L /K$, a $K-$automorphism of $L$ is an automorphism of $L$ which fixes $K$. The set of all such $K-$automorphisms forms a group denoted $\mathrm{Aut}(L/K)$.

From each intermediate field $K \subset F \subset L$, we get a subgroup $\mathrm{Aut}(L/F) := \{\sigma \in \mathrm{Aut}(L/K) | \sigma(a) = a \ \forall \ a \in F\}$ of $\mathrm{Aut}(L/K)$.
And, given any subgroup $H \le \mathrm{Aut}(L/K)$, we get a corresponding intermediate field $K \subset L^H \subset L$, where $L^H := \{\alpha \in L : \sigma(\alpha) = \alpha \ \forall \ \sigma \in H\}$, this is called the fixed field of $H$.

It is straightforward to check that $F \subset L^{\mathrm{Aut}(L/F)}$ and $H \subset \mathrm{Aut}(L/L^H)$.
The galois correspondence gives descriptions of those extensions $L/K$ where the above two inclusions become equalities.

This will give us, at a minimum, $K = L^{\mathrm{Aut}(L/K)}$.
This is not true for general extensions. Consider $L = \mathbb{Q}(\sqrt[3]{2})$ and $K = \mathbb{Q}$ this has no intermediate fields and its automorphism group is trivial. Which gives the fixed field of $\mathrm{Aut}(L/K) = L$ which is not desirable in context to the above discussion.

This problem arose because some roots of the min poly of $\sqrt[3]{2}$ were missing from the extension, so there was only one option of sending $\sqrt[3]{2}$ under an automorphism, to itself.

Another type of problem we encounter is the following:
Let $p$ be a prime and $F = \mathbb{F}_p$ then $X^p - u$ has only one root in the splitting field over $F(u)$ (the polynomial in consideration is inseparable). Hence $\mathrm{Aut}(\mathbb{F}_p(u^{1/p})/\mathbb{F}_p(u))$ is trivial, while the degree of the extension is $p$. 

This problem arose because the extension in question was not separable, hence didn't have enough roots for the $\mathrm{Aut}$ group to be non trivial. 
```

### Lemma 1:
```ad-note
title:
If $\sigma \in \mathrm{Aut}(L/K)$ and $f(X) \in K[X]$ then $\sigma(f(\alpha)) = f(\sigma(\alpha))$ for all $\alpha \in L$. In particular, a $K-$ automorphism permutes the root of any polynomial over $K$.
```

### Theorem 1:
```ad-note
title:
For every finite extension $L /K$, the group $\mathrm{Aut}(L /K)$ is finite.
```
##### Proof:
Write $L = K(\alpha_{1},\alpha_{2},\dots,\alpha_{n})$, and each $\sigma \in \mathrm{Aut}(L/K)$ is determined by the image of all $\alpha_{i}$'s. 
Each $\alpha_{i}$ has only finitely many possible images, its conjugates. Hence the number of $\sigma$'s is finite.

### Theorem 2:
```ad-note
title:
If $L$ is a splitting field over $K$ of a polynomial in $K[X]$, then $|\mathrm{Aut}(L/K)| \le [L:K]$.
```
##### Proof:
Apply Theorem 1 of [[Splitting Fields]] to $L_{1} = L_{2} = L$, we get from part (c) that the number of isomorphisms which extend $id_{K}: K \to K$ is at most $[L : K]$, which was desired.

### Theorem 3:
```ad-note
title:
If $L$ is a splitting field over $K$ of a **separable** polynomial in $K[X]$, then $|\mathrm{Aut}(L/K)| = [L:K]$.
```
##### Proof:
Apply theorem 3 of [[Splitting Fields]] to $L_{1} = L_{2} = L$ and $K_{1} =K_{2} = K$.

#### We want to look at those field extensions where $|\mathrm{Aut}(L /K)| = [L : K]$. Previous theorem has a converse.

### Theorem 4:
```ad-note
title:
If $L /K$ is a finite extension and $|\mathrm{Aut}(L /K)| = [L  :K]$ then
1) $L ^{\mathrm{Aut}(L /K)} = K$
2) $L /K$ is separable.
3) For $\alpha \in L$, its $K-$conjugates are $\sigma(\alpha)$ as $\sigma$ runs over $\mathrm{Aut}(L)$.
4) $L/K$ is normal.
5) $L$ is the splitting field over $K$ of a separable polynomial.
```
##### Proof:
First we show that (2) and (4) imply (5).
Since $L /K$ is separable, using primitive element theorem, we get $L =K(\gamma)$. Let $f$ be the min poly of $\gamma$ over $K$. Then since $L /K$ is normal, $f$ splits completely in $L$, thus $L$ is the splitting field of $f$ over $K$.

Now for the first 4 conditions.
Set $F = L ^{\mathrm{Aut}(L /K)}$, this gives $\mathrm{Aut}(L /K) \subset \mathrm{Aut}(L /F)$. But we always have $\mathrm{Aut}(L /F) \subset \mathrm{Aut} (L /K)$, hence $\mathrm{Aut}(L /K) = \mathrm{Aut}(L /F)$, this gives $F = L ^{\mathrm{Aut}(L /F)}$.
Now we prove (2),(3) and (4) for $F$ instead of $K$ and then show that $F = K$.

For (2),
pick an $\alpha \in L$, let $S = \{ \sigma(\alpha) : \sigma \in \mathrm{Aut}(L /F) \} = \{ \sigma_{i}(\alpha) : i = 1 ,2,\dots, m \}$. 
Define $h(X) := \prod \limits_{ i=1}^{ m } (X - \sigma_{i}(\alpha))$, we show that $h \in K[X]$, since we know $h$ has distinct roots by definition, we will have a separable poly with root $\alpha$. 
Now notice that for any given $\sigma \in \mathrm{Aut}(L /F), \ \sigma(\sigma_{i}(\alpha)) = \sigma_{j}(\alpha)$ for some $j$. Hence any $\sigma$ takes $S$ to itself injectively and hence bijectively. Therefore, $\sigma(h(X)) = \prod\limits_{ i=1}^{ m }(X - \sigma_{i}(\alpha)) = h(X)$, this gives $h(X) \in F[x]$.

For (3),
we show that $h(X)$ is the minimal poly of $\alpha$ in $F$. This is easy, just take any poly $f$ with $\alpha$ as a root and it is easy to see that $\sigma(\alpha)$ is a root of $f$ too, for all $\sigma$. Hence, $h | f$ and so $h$ is the min poly of $\alpha$ in $F$.

For (4),
Let $f$ be an irreducible poly in $F[X]$ with a root $\gamma \in L$. We have shown that $h_{\gamma}(X) = \prod\limits_{ i=1}^{ m } (X - \sigma(\gamma))$ is the minimal poly of $\gamma$ over $F$, hence $h_{\gamma} = f$. Hence all the conjugates of $\gamma$ lie in $L$, hence $f$ splits in $L$.

Now to show that $F = K$,
We have that (2) and (4) hold for $F$ in place of $K$, hence by (5), $L$ is the splitting field of a separable poly over $F$. Hence by the previous theorem, $|\mathrm{Aut}(L /F)| = [L : F]$ which gives $|\mathrm{Aut}(L /K)| = [L : K] = [L:F]$ and hence, $K = F$.


---
# Examples:
1. Let $K = \mathbb{Q}$, and $L = \mathbb{Q}(\sqrt[3]{2},\omega)$ where $\omega$ is a non trivial cube root of unity. The polynomial $X^{3}-2$ has 3 roots in $L$. Each $K-$automorphism of $L$ permutes these 3 roots. Check that all 6 permutations are realized by $K-$automorphisms of $L$.
2. Let $K = \mathbb{Q}$ and $L = \mathbb{Q}(\sqrt[4]{ 2},i)$. The poly $X ^{4} - 2$ has all four roots in $L$. These 4 roots have 24 permutations possible, but not all of them are realised by $\mathrm{Aut}(L/K)$. The automorphism group is actually $D_{8}$ (the dihedral group of the square).
3. $|\mathrm{Aut}(\mathbb{Q}(\sqrt[4]{ 2 }) /\mathbb{Q})| = 2$ but $[\mathbb{Q}(\sqrt[4]{ 2 }) : \mathbb{Q}] = 4$

---
# References
[[Separable Extensions]]
[[Separable Polynomials]]
[[Splitting Fields]]
[[Normal Extensions]]
[[Primitive Element Theorem]]
[[Extension Field]]
