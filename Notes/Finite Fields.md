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

### Lemma 2:
```ad-note
title:
Every finite field has prime power order.
```


### Lemma 3:
```ad-note
title:
Every finite field $F$ is of the form $\mathbb{F}_p[X] / (\pi(X))$ for some prime $p$ and some monic irreducible $\pi(X) \in \mathbb{F}_p[X]$.
```
###### Proof:
Since $F ^{\times}$ is cyclic, it has a generator $\gamma$, now take the homomorphism $\phi : \mathbb{F}_{p}[X] \to F$ which is just evaluation at $\gamma$. This is a surjective homomorphism. Hence, $F = \mathbb{F}_{p}[X]/ ker (\phi)$. But $ker(\phi) = (\pi(X))$ for some monic irreducible polynomial $\pi(X)$ since $ker(\phi)$ is a maximal ideal ($F$ is a field) and $\mathbb{F}_{p}[X]$ is a PID.

### Lemma 4:
```ad-note
title:
A field of prime power order $p^n$ is a splitting field over $\mathbb{F}_p$ of $x^{p^n} - x$.
```
###### Proof:
Let $F$ be a field of order $p ^{n}$, then each element in $F$ satisfies $x ^{p ^{n}} - x$ and so it splits in $x ^{p ^{n}}-x$.

---
### Theorem 1:
```ad-note
title:
For every prime power $p^n$, a field of that order exists.
```
###### Proof:
Let $F$ be the splitting field of $x ^{p ^{n}}-x$ over $\mathbb{F}_{p}$. Then this contains a subfield consisting of the roots of $x ^{p ^{n}}-x$ (show that this is a subfield).

Now show that $f(x) = x ^{ p ^{n}}-x$ is separable.
$f'(x) = -1$ and so, $(f(x),f'(x)) = 1$, therefore $f$ is separable. And so, the number of roots of $f$ is $p ^{n}$.

### Lemma 5:
```ad-note
title:
Each irreducible $\pi(X)$ in $\mathbb{F}_p[X]$ of degree $n$ divides $x^{p^n}-x$ and is separable.
```
###### Proof:
$\mathbb{F}_{p}[X] /(\pi(X))$ is of degree $n$ over $\mathbb{F}_{p}$ and so is of size $p^n$, hence $t ^{p ^{n}}  = t$ for all $t \in \mathbb{F}_{p}[X] /(\pi(X))$, in particular, $x ^{ p ^{n}} = x \ (\mathrm{mod}\ \pi(x))$ and so, $\pi(x) | x ^{ p ^{n}}-x$. And since $x ^{ p ^{ n}}-x$ is separable, $\pi(x)$ is too.

### Theorem 2:
```ad-note
title:
All finite fields of the same size are isomorphic to one another.
```

---
---
# References
[[Abelian Groups]]
[[Splitting Fields]]