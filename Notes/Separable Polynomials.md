202303071403

Type : #Note
Tags : [[Algebra]]

---
# Separable Polynomials
```ad-note
title:
A polynomial $f(x) \in K[x]$ is called **separable** when it has distinct roots in a splitting field over $K$. If $f(x)$ has repeated roots in the splitting field, then it is called **inseparable**.
```

### Theorem 1: 
```ad-note
title:
A non zero polynomial in $K[X]$ is separable iff it is relatively prime to its derivative in $K[X]$.
```
##### Proof:
Let $f(X)$ be a separable poly in $K[X]$. Let $\alpha$ be a root of $f(X)$, then $f(X) = (X-\alpha)g(X)$. Differentiating this we get $f'(X) = g(X) + (X-\alpha)g'(X)$.
But since $g(\alpha) \neq 0$ ($f$ is separable and $\alpha$ is a root of $f$), we get that $f'(\alpha) \neq 0$. Therefore, $f'$ and $f$ have no common roots and hence are relatively prime.

Now suppose $f(X)$ is NOT separable, then by definition of separability, it has a repeated root say $\alpha$. Then $f(X) = (X - \alpha)^{2}g(X)$, differentiating this we get $f'(X) = 2(X-\alpha)g(X) + (X-\alpha)^{2}g(X)$, this has $\alpha$ as a root, and so $f$ and $f'$ are not relatively prime.

### Lemma 1:
```ad-note
title:
$f(X) = X ^{n}-a$ is separable over $K$ ($a \in K ^{\times}$) iff $n\neq 0$ in $K$.
```
##### Proof:
Let $f(X) = X ^{n}-a$ where $a \in K ^{\times}$. The derivative $f'(X) = nX ^{n-1}$. This is zero if $n = 0$ in $K$, in which case $(f,f') = f$ and hence $f$ is not separable. If $n \neq 0$, then $(X ^{n}-a,nX ^{n-1}) = 1$ since $X$ does not divide $X ^{n}-a$.
This establishes the lemma.

### Lemma 2:
```ad-note
title:
If $K$ has characteristic $p$, and $g(X ^{p}) \in K[X ^{p}]$ is an arbitrary polynomial in $X ^{p}$ and $c \in K ^{\times}$ then $g(X ^{p}) + cX$ is separable in $K[X]$.
```

### Corollary 1 to Theorem 1: 
```ad-note
title:
If $f(X) \in K[X]$ is separable and $L \supset K$ then every factor of $f(X)$ in $L[X]$ is also separable. An element in an extension of $L$ that is separable over $K$ is also separable over $L$.
```
##### Proof:
Let $g(X)$ be a factor of $f(X)$, say $f(X) = g(X)h(X)$ in $L[X]$. 
Since $f(X)$ is separable we can write $1 = f(X)u(X) + f'(X)v(X)$ for some polynomials $u(X)$ and $v(X)$ in $K[X]$. 
Then $1 = (g(X)h(X))u(X) + (g(X)h'(X) + g'(X)h(X))v(X) = g(X)(h(X)u(X) + h'(X)v(X)) + g'(X)(h(X)v(X))$. 
The last expression shows a polynomial-linear combination of $g(X)$ and $g'(X)$ equals 1, so $g(X)$ is separable. 

Suppose $\alpha$ is in an extension of $L$ and it is separable over $K$. Since its minimal polynomial in $L[X]$ divides its minimal polynomial in $K[X]$, separability of $\alpha$ over $K$ implies separability of $\alpha$ over $L$ by what we just showed above.

### Corollary 2 to Theorem 1:
```ad-note
title:
Let $K$ and $L$ be fields. If $\sigma : K\to L$ is a field embedding, then a polynomial $f(X) \in K[X]$ is separable iff $(\sigma f)(X)$ is separable in $L[X]$.
```
##### Proof:
Let $f$ be separable in $K[X]$, then we have $u,v \in K[X]$ such that 
$$
f(X)u(X) + f'(X)v(X) = 1
$$
This gives 
$$
\sigma f(X) \sigma u(X) + \sigma f'(X) \sigma v(X) = \sigma(1) = 1_{L}
$$
This means that $\sigma f$ is separable in $L[X]$.

Now assume $f(X)$ is inseparable, then $d = (f,f')$ hence $\sigma d = (\sigma f,(\sigma f)')$ hence $\sigma f$ is inseparable.

### Theorem 2:
```ad-note
title:
For every field $K$, an irreducible polynomial in $K[X]$ is separable iff its derivative is non zero in $K[X]$.
```

###### Note: This means that if $\mathrm{char}\ K = 0$ then every irreducible poly is separable, and if $\mathrm{char} \ K = p$, then an irreducible poly is separable iff it is NOT a poly in $X ^{p}$.
##### Proof:
Let $\pi(X)$ be irreducible in $K[X]$, now $\pi(X)$ is _inseparable_ iff $(\pi(X),\pi'(X)) \neq 1$ which is equivalent to saying that $\pi(X) | \pi'(X)$ since $\pi$ is irreducible. But since $\mathrm{deg}(\pi') < \mathrm{deg}(\pi)$, we get that $\pi'(X) \equiv 0 \iff \pi(X)$ is inseparable.

### Theorem 3:
```ad-note
title:
The roots of an inseparable irreducible poly in characteristic $p$, all have multiplicity a common power of $p$.
```



---
# Related Problems
[[Separable Extensions]]

---
# References
[[Splitting Fields]]