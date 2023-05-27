202304161704

Type : #Note
Tags : [[Algebra]]

---
# Galois Extensions
```ad-note
title:
A finite extension is called _Galois_ when it is both normal and separable. When $L /K$ is Galois, the group $\mathrm{Aut}(L /K)$ is denoted $\mathrm{Gal}(L /K)$ and is called the _Galois group_ of the extension.
```

### Theorem 1:
```ad-note
title:
For a finite extension $L /K$, TFAE:
1. $|\mathrm{Aut}(L /K)| = [L : K]$
2. $L ^{\mathrm{Aut}(L /K)} = K$
3. $L /K$ is normal and separable.
4. $L$ is the splitting field over $K$ of a separable polynomial in $K[X]$.
```
##### Proof:
We know from Theorem 4 in [[Galois Correspondence]] that (1) implies (2),(3),(4).
We also showed in the proof of this theorem that (3) implies (4)
Use the construction of $h(X)$ as in the proof of the theorem mentioned above to show (2) implies (3).

We know from [[Splitting Fields]] (corollary to theorem 3) that (4) implies (1).
$mathrm{Aut}()$

### Corollary:
```ad-note
title:
If $L/K$ is a finite extension then $|\mathrm{Aut}(L/K)| \mid [L:K]$.
```
##### Proof:
Since $L /K$ is finite, the order of the group $\mathrm{Aut}(L /K)$ is finite.
Let $F = L ^{\mathrm{Aut}(L /K)}$, we know $\mathrm{Aut}(L /F) = \mathrm{Aut}(L /K)$.
So, $F = L ^{\mathrm{Aut}(L /F)}$ hence by the previous theorem, $|\mathrm{Aut}(L /F)| =[L:F] \mid [L:K]$, hence we get that
$$
|\mathrm{Aut}(L /K)| \mid [L:K]
$$
### Corollary:
```ad-note
title:
If $L /K$ is a finite extension which is either inseparable or not normal, then $|\mathrm{Aut}(L/K)| < [L:K]$
```

### Theorem 2:
```ad-note
title:
Every finite separable extension of a field can be enlarged to a finite Galois extension of the field. In particular, every finite extension of a field with characteristic 0 can be enlarged to a finite galois extension.
```
##### Proof:
Take $L = K(\alpha)$ ([[Primitive Element Theorem]]), then we can extend $L$ by adding all roots of the minimal polyomial of $\alpha$ over $K$, to $K$. This gives a galois extension of $K$ extending $L$ as well.

### Theorem 3:
```ad-note
title:
If $L /K$ is a finite galois extension and $F$ is an intermediate field, then $L /F$ is galois as well.
```
##### Proof:
Take $\alpha \in L$, take its min poly over $K$, call it $\pi_{\alpha}$, since $\alpha$ is separable over $K$, $\pi_{\alpha}$ is separable. 
Then the min poly of $\alpha$ over $F$ divides $\pi_{\alpha}$, and hence it has distinct roots since $\pi_{\alpha}$ does, and so is separable. This means $L /F$ is separable.
Now take any irreducible poly $f$ in $F$, let it have a root $\gamma$ in $L$. This has a min poly $\pi_{\gamma}$ over $K$. Since $L$ is normal over $K$, $\pi_{\gamma}$ splits completely in $L$. Now $f | \pi_{\gamma}$ and hence it splits in $L$ as well. Thus $L /F$ is normal.

###### NOTE: The bottom part of the tower $F /K$ need not be galois when $L /K$ is. Also, if $L /F$ and $F /K$ are galois, $L /K$ need not be galois (See example 3)

### Theorem 4:
```ad-note
title:
If $L_{1},L_{2}$ are finite galois extensions of $K$ inside a common field then $L_{1}L_{2}$ and $L_{1} \cap L_{2}$ are both finite galois extensions of $K$.
```
##### Proof:
Call the common field $L$.
Due to Corollary 2.2 of [[Separable Extensions]], we get that $L_{1}, L_{2}$ are subfields of the field of separable elements in $L$ over $K$ (call this $F$). Hence $L_{1}L_{2}$ and $L_{1} \cap L_{2}$ are subfields of $F$, hence separable over $K$.
Now take $\alpha \in L_{1} \cap L_{2}$, then its min poly over $K$ has all its conjugates in $L_{1}$ and in $L_{2}$, hence in $L_{1} \cap L_{2}$. Thus $L_{1} \cap L_{2}$ is normal, and so galois.

For $L_{1}L_{2}$, observe that $L_{i}$ is the splitting field of a separable poly $f_{i}$ over $K$ for $i=1,2$.
Thus $L_{1}L_{2}$ is the splitting field of $f_{1}f_{2}$ (removing repeated factors). 



---
# Examples
1. The extension $\mathbb{Q}(\sqrt[3]{ 2 },\omega) / \mathbb{Q}$ is a galois extension since it's the splitting field of $X^{3}-2$ over $\mathbb{Q}$.
   So by theorem 1, $|\mathrm{Gal}(\mathbb{Q}(\sqrt[3]{2  },\omega) /\mathbb{Q})| = 6$.
   Now we know that any autmorphism of this field is determined by the images of $\omega, \sqrt[3]{ 2 }$. But we have two possibilities for $\omega$, and 3 for $\sqrt[3]{ 2 }$, hence totally 6 possibilities. But since the size of the galois group is 6, we know all of these possibilities are achieved. 

   To look at this another way, any automorphism is also determined by what it does to the roots $\sqrt[3]{ 2 }, \omega\sqrt[3]{ 2 }, \omega^{2} \sqrt[3]{ 2 }$, and there are again 6 possibilities for this, so all of them are achieved.
   In other words, $\mathrm{Gal}(\mathbb{Q}(\sqrt[3]{ 2 },\omega)/\mathbb{Q}) = S_{3}$.

2. The extension $\mathbb{Q}(\sqrt[4]{ 2 },i) / \mathbb{Q}$ is galois.
   The degree of this extension is 8. Hence, $|\mathrm{Gal}(\mathbb{Q}(\sqrt[4]{ 2 }, i) /\mathbb{Q})| = 8$. Since $\sqrt[4]{ 2 }$ has 4 choices, and $i$ has 2 choices, any assignment of $\sigma(\sqrt[4]{ 2 })$ and $\sigma(i)$ to roots of $X ^{4}-2$ and $X ^{2}+1$ must be realised by field automorphisms.
   Imagine the 4 roots of $X ^{4}-2$ as the vertices of a square, it can be shown with a bit of work that the galois group is just the group of symmetries of this square, which is $D_{8}$.

3. Let $L = \mathbb{Q}(\sqrt[4]{ 2 },i)$ and $K = \mathbb{Q}$, take $F = \mathbb{Q}(\sqrt[4]{ 2 })$, then $F /K$ is not galois even though $L /K$ is.
   Let $L = \mathbb{Q}(\sqrt[4]{ 2 })$ and $K = \mathbb{Q}$, take $F = \mathbb{Q}(\sqrt[]{ 2 })$, then $L /K$ is not galois even though $L /F$ and $F /K$ are.  

---
# References
[[Normal Extensions]]
[[Separable Extensions]]
[[Galois Correspondence]]
[[Splitting Fields]]
[[Primitive Element Theorem]]
[[Extension Field]]