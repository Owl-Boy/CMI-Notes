202303071403

Type : #Note
Tags : [[Algebra]]

---
# Separable elements
```ad-note
title:
If $\alpha$ is algebraic over $K$, it is called _separable_ over $K$ if its minimal polynomial over $K$ is separable.
```

# Separable Extensions
```ad-note
title:
A finite extension $L/K$ is called separable if every element of $L$ is separable over $K$. Otherwise it is called inseparable.
```

### Theorem 1:
```ad-note
title:
Let $L /K$ be a finite extension with $[L:K] = n$ and $\sigma : K \to F$ be a field embedding.

(a) The number of extensions of $\sigma$ to an embedding $L \to F$ is at most $n$.

(b) If $L /K$ is inseparable, the number of extensions is strictly less than $n$.

(c) If $L /K$ is separable, then there is a field $F' \supset F$ such that the number of extensions of $\sigma$ to an embedding $L \to F'$ is equal to $n$.
```
##### Proof:
(a) Proof proceeds by induction on $n$.
Let $\alpha$ be an element in $L \setminus K$, then $K(\alpha)$ is an intermediate field between $L$ and $K$. We show that the number of extensions of $\sigma$ to an embedding $K(\alpha) \to F$ is at most $[K(\alpha) : K]$, then by induction we will get that the number of extensions of the resulting embedding is at most $[L:K(\alpha)]$ which will give the number of extensions of $\sigma$ to $L \to F$ is at most $[L:K]$ as desired.

Let $\pi_{\alpha}$ be the minimal poly of $\alpha$ over $K$. Then $\pi_{\alpha}(\alpha) = 0$, this means that $\sigma \pi_{\alpha}(\sigma(\alpha)) = 0$ which implies that $\sigma(\alpha)$ is a zero of $\sigma \pi_{\alpha}$ of which there are at most $\mathrm{deg}(\sigma \pi_{\alpha}) = \mathrm{deg}(\pi_{\alpha}) = [K(\alpha) : K]$ many. And since the extension of $\sigma$ to $K(\alpha)$ is determined by its image on $\alpha$, we get that there are at most $[K(\alpha):K]$ many extensions.

(b) If $L/K$ is inseparable, there is some element $\alpha$ of $L$ whose minimal poly $\pi_{\alpha}(X)$ has repeated roots, hence $\sigma \pi_{\alpha}$ has repeated roots, which means that the number of extensions of $\sigma$ are strictly less than the degree of $\pi_{\alpha}$ and hence $[K(\alpha):K]$.

(c)
#### Claim:
```ad-note
title:
Let $L = K(\alpha_{1},\alpha_{2},\dots,\alpha_{n})$, and let $\pi_{i}(X)$ be the minimal polynomial for $\alpha_{i}$ in $K$ for each $i$.

Let $F' /F$ be a field extension in which each $\sigma \pi_{i}$ splits completely. Then we claim that $\sigma$ has $[L:K]$ extensions to embeddings of $L$ into $F'$.
```
Look at $\sigma$ as an embedding of $K$ into $F'$ now.
Consider $K(\alpha_{1}) /K$, the number of extensions of $\sigma$ to $K(\alpha_{1})$ = $\mathrm{deg}(\pi_{1}) = [K(\alpha_{1}):K]$. If $L = K(\alpha_{1})$ then we are done.
Otherwise, $L = K(\alpha_{1})(\alpha_{2},\dots,\alpha_{n})$ and pick an embedding $\tau : K(\alpha_{1}) \to F'$ out of the $\mathrm{deg}(\pi_{1})$ extensions of $\sigma$. Now take $m_{i}(X)$ to be the minimal polys of $\alpha_{i}$ over $K(\alpha_{1})$ for $i = 2,\dots ,n$. We know that $m_i | \pi_{i}$ and so, $\tau m_{i} | \tau \pi_i = \sigma \pi_{i}$.
Since $\sigma \pi_{i}$ is separable and splits completely in $F'$, so does $\tau m_{i}$

This means that $L , K(\alpha_{1})$ and the $m_{i}$'s satisfy the condition in the claim and hence we get by induction, that $\sigma$ has $[L : K(\alpha_{1})]$ extensions to $L$. Hence we get there are $[L:K(\alpha_{1})][K(\alpha_{1}):K]$ extensions to $\sigma$.

### Theorem 2:
```ad-note
title:
Let $L /K$ be a finite extension and let $L = K(\alpha_{1},\alpha_{2},\dots ,\alpha_{n})$. Then $L/K$ is separable iff all the $a_{i}$'s are.
```
##### Proof:
If all the $a_{i}$'s are separable over $K$, then we can follow the proof of theorem 1 (c) with $F = K$ and $\sigma = id_{K}$. So we get that there are $[L:K]$ extensions of $\sigma$ to embeddings of $L$ into a field extension of $K$.
And so by Theorem 1 (b), we get that $L /K$ cannot be inseparable. Hence $L /K$ is separable.

### Corollary 2.1:
```ad-note
title:
If $f(X) \in K[X]$ is separable then a splitting field for $f$ over $K$ is separable over $K$.
```
##### Proof:
Let $L /K$ be a splitting field for $f$. Then $L = K(\gamma_{1},\gamma_{2},\dots,\gamma_{n})$ where $\gamma_{i}$ are the roots of $f$. Therefore the $\gamma_{i}$'s are separable over $K$ and hence so is $L$.

### Corollary 2.2:
```ad-note
title:
Given any finite extension $L /K$, the set of all elements of $L$ that are separable over $K$ form a subfield.
```
##### Proof:
Take two elements $\alpha, \beta$ in $L$ that are separable over $K$, then $K(\alpha,\beta)$ is a separable over $K$. Thus $\alpha \pm \beta$, $\alpha\beta$, $\alpha^{-1}$ are all separable. Hence the set of separable elements form a subfield.

### Theorem 3:
```ad-note
title:
If $E/L/K$ is a tower of finite extensions, then $E/K$ is separable iff $E/L$ and $L/K$ are separable.
```
##### Proof:
One direction is easy.
Now suppose $E/L$ and $L /K$ are separable.
Take a field embedding $\sigma : K\to F$, then there is an extension $F' /F$ s.t. $\sigma$ extends to $[L : K]$ embeddings of $L$ to $F'$. Now take any one of these, and that will extend to $[E:L]$ embeddings of $E$ into an extension $F''/F'$.
This means that $\sigma$ extends to $[E:K]$ embeddings of $E$ into $F'' /F$.
Thus $E/K$ is separable by Theorem 1.



---
# Related Problems
[[Primitive Element Theorem]]

---
# References
[[Extension Field]]
[[Splitting Fields]]
[[Separable Polynomials]]

