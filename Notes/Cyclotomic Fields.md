202306012006

Type : #Note
Tags : [[Number Theory]]

---
# Cyclotomic Fields
```ad-note
title:
Let $\omega = e ^{2\pi i/m}$, where $m > 1$ is an integer. Then the field $\mathbb{Q}(\omega)$ is called the $m ^{th}$ cyclotomic field.
```
It can be seen that:
- For odd $m$, the $m ^{th}$ cyclotomic field is equal to the $2m ^{th}$ one. ($e ^{2\pi i/2m} = -e ^{2\pi i(m+1)/2m} \in \mathbb{Q}[e ^{2\pi i/m}]$).
- The field is a finite extension of $\mathbb{Q}$.

### Theorem 1:
```ad-note
title:
All $\omega^{k}$, $1 \le k \le m$, $(m,k) = 1$, are exactly the conjugates of $\omega$.
```
###### Proof:
It is easy to see that every conjugate of $\omega$ is also a root of $x^{m}-1$ but not of $x ^{n}-1$ for all $n < m$.
But these are the numbers $\omega^{k}$ with $1 \le k \le m, \ (m,k) = 1$. Thus the set of conjugates is contained in the set $S = \{ \omega^{k} : 1 \le k \le m, (m,k) = 1 \}$.

Consider the field homomorphism $\sigma : \mathbb{Q}(\omega) \to \mathbb{Q}(\omega)$ which takes $\omega$ to $\omega^{k}$ and fixes $\mathbb{Q}$ for some $1 \le k \le m$, $(k,m) = 1$.
Now, $\omega \in \sigma(\mathbb{Q}(\omega))$. Why? Because $(k,m) = 1$, and so $um+vk =1$ for some $u,v \in \mathbb{Z}$.
Thus, $\omega = \omega^{um+vk} = (\omega^{k})^{v} = \sigma(\omega^{v})$. So $\sigma$ is a linear map from a finite dimensional $\mathbb{Q}$-vector space to itself, which is injective (since it's a non zero field homomorphism).

This makes it a vector space isomorphism, and hence a field automorphism fixing $\mathbb{Q}$.
Note that $\mathbb{Q}(\omega)$ is a galois extension of $\mathbb{Q}$, since it is the splitting field of $x ^{m}- 1$ over $\mathbb{Q}$.
This makes $\sigma$ a member of $\mathrm{Gal}(\mathbb{Q}(\omega) /\mathbb{Q})$, implying $\varphi(m) = |S| \le |\mathrm{Gal}(\mathbb{Q}(\omega) /\mathbb{Q})| = deg(\omega) \le \varphi(m)$.
This means $|\mathrm{Gal}(\mathbb{Q}(\omega) / \mathbb{Q})| = \varphi(m) = deg(\omega)$, and so $S =$ the set of conjugates of $\omega$.

### Corollary:
```ad-note
title:
$\mathbb{Q}(\omega)$ has degree $\varphi(m)$ over $\mathbb{Q}$.
```

### Corollary:
```ad-note
title:
$\mathrm{Gal}(\mathbb{Q}(\omega) / \mathbb{Q})$ is isomorphic to the multiplicative group of integers mod $m$. For each $k$, the corresponding automorphism sends $\omega$ to $\omega^{k}$ as in the proof.
```

#### Note:
By the fundamental theorem of galois theory, we find that subfields of $\mathbb{Q}(\omega)$ and subgroups of $\mathbb{Z}_{m}^{*}$ are in correspondence with each other. In particular, for $p ^{th}$ cyclotomic fields, with $p$ an odd prime, there is a unique quadratic field (since $\mathbb{Z}_{p}^{*}$ is of order $p-1$ and cyclic).
It turns out that this field is in fact $\mathbb{Q}[\sqrt[]{ \pm p }]$.
The proof follows from Theorem 1 in [[Gauss sums]]

### Corollary:
```ad-note
title:
Let $\omega = e ^{2\pi i/m}$. If $m$ is even, the only roots of $1$ in $\mathbb{Q}[\omega]$ are the $m ^{th}$ roots of unity. If $m$ is odd, the only ones are the $2m ^{th}$ roots of unity.
```
###### Proof:
The second part follows from the first and the fact that $2m ^{th}$ cyclotomic field is equal to the $m ^{th}$ one, if $m$ is odd.

To prove the first part, suppose $\theta$ is a primitive $k ^{th}$ root of unity in $\mathbb{Q}(\omega)$. Then there is a primitive $r ^{th}$ root of unity in $\mathbb{Q}(\omega)$ where $r = lcm(k,m)$. Implying $\phi(r) \le \phi(m)$, but since $r = \frac{km}{gcd(k,m)} = k'm$ where $gcd(k',m) = 1$, we get $\phi(r) = \phi(k')\phi(m) \le \phi(m) \implies \phi(k') \le 1 \implies k' = 1 \ \text{or} \ 2$. But $k'$ can't be 2 since it is coprime to $m$, thus $k' = 1$ giving $r = m$.
Hence, $k \mid m$ and $\theta$ is an $m ^{th}$ root of unity.

### Corollary:
```ad-note
title:
The $m ^{th}$ cyclotomic fields, for $m$ even, are all distinct, and pairwise non isomorphic.
```

---
# Ring of integers of Cyclotomic fields
### Theorem 2:
```ad-note
title:
Let $\omega = e ^{2\pi i/m}$, where $m = p ^{r},p$ a prime. Then $\overline{\mathbb{Z}}\cap \mathbb{Q}(\omega) = \mathbb{Z}[\omega]$.
```

### Lemma 1:
```ad-note
title:
For $m \ge 3$,
$\mathbb{Z}[\omega] = \mathbb{Z}[1-\omega]$ and $\mathrm{disc}(\omega) = \mathrm{disc}(1-\omega)$.
```
###### Proof:
$\mathbb{Z}[\omega] = \mathbb{Z}[1-\omega]$ is clear.
$$
\mathrm{disc}(\omega) = \prod_{1 \le r < s\le n} (\alpha_{r}-\alpha_{s})^{2} =\prod_{1 \le r < s\le n} (1-\alpha_{r}-(1-\alpha_{s}))^{2} = \mathrm{disc}(1-\omega) 
$$

### Lemma 2:
```ad-note
title:
For $m = p ^{r}$, 
$$
\prod_{k}(1-\omega^{k}) = p
$$
where the product is over all $1\le k \le m$ such that $(k,p) = 1$
```
###### Proof:
Set $f(x) = \frac{x ^{p ^{r}}-1}{x ^{p ^{r-1}}-1} = 1+ x ^{p ^{r-1}} + \dots + x ^{(p-1)p ^{r-1}}$.
Then all $\omega^{k}$ ($k$ as above) are roots of $f$.
Thus $f(x) = \prod_{k}(x-\omega^{k})$ since there are exactly $\phi(p ^{r})$ values of $k$. Now set $x = 1$.

###### Proof of Theorem:
By theorem 1 of [[Number Rings]], every $\alpha \in R$ can be expressed in the form $$
\alpha = \frac{m_{1} + m_{2}(1-\omega) + \dots m_{n}(1-\omega)^{n-1}}{d}
$$
where $n = \phi(p ^{r})$, and $d = \mathrm{disc}(\omega) = \mathrm{disc}(1-\omega)$.
We know that $\mathrm{disc}(\omega) \mid m ^{\phi(m)}$ ([[Discriminant of an n-tuple]]/ related problems/ problem 2), thus $\mathrm{disc}(1-\omega)$ is a power of $p$.
Now suppose there is an $\alpha \in R$ such that some $m_{i}$ is not divisible by $d$, then $R$ contains
$$
\beta = \frac{m_{i}(1-\omega)^{i-1} + \dots + m_{n}(1-\omega)^{n-1}}{p}
$$
where $p \nmid m_{i}$ (because, we can take $m_{i}$ to be the one with the least power of $p$, then cancel out all prime powers with $d$ until $p \nmid m_{i}$ and multiply everything by a suitable power of $p$ until only $p$ remains in the denominator, and then remove terms of the form $\mathbb{Z}(1-\omega)^{k}$).

Lemma 2 gives $\frac{p}{(1-\omega)^{n}} \in \mathbb{Z}[\omega]$. Then $\frac{p}{(1-\omega)^{i}} \in \mathbb{Z}[\omega]$ and hence $\frac{\beta p}{(1-\omega)^{i}} \in R$. Implying $\frac{m_{i}}{(1-\omega)} \in R$. It follows that $N(1-\omega) | N(m_{i}) \implies p | m_{i}^{\phi(m)}$ a contradiction.

Thus $R = \mathbb{Z}[1-\omega] = \mathbb{Z}[\omega]$.

### Theorem 3:
```ad-note
title:
Let $K = \mathbb{Q}(\omega), \omega = e ^{2\pi i/m}, R = \overline{\mathbb{Z}}\cap K$. Then $R = \mathbb{Z}[\omega]$.
```
###### Proof:
We know this holds for $m = p ^{r}$.
We induct on the number of distinct prime factors.
Let $m = p_{1} ^{r_{1}}p_{2}^{r_{2}}$.
Let $\omega_{1} = e ^{2\pi i/p_{1}^{r_{1}}}$ and $\omega_{2} = e ^{2\pi i/p_{2}^{r_{2}}}$, $\omega = e ^{2\pi i/m}$
Then $\mathbb{Q}(\omega) = \mathbb{Q}(\omega_{1})\mathbb{Q}(\omega_{2})$ and $\mathbb{Z}[\omega] = \mathbb{Z}[\omega_{1}]\mathbb{Z}[\omega_{2}]$.
Since $d = \mathrm{gcd}(\mathrm{disc}(\mathbb{Z}[\omega_{1}]),\mathrm{disc}(\mathbb{Z}[\omega_{2}])) = \mathrm{gcd}(p_{1}^{t_{1}},p_{2}^{t_{2}}) = 1$, therefore by corollary 1 to theorem 3 in [[Number Rings]], we get $\overline{\mathbb{Z}} \cap \mathbb{Q}(\omega) = \mathbb{Z}[\omega_{1}]\mathbb{Z}[\omega_{2}] = \mathbb{Z}[\omega]$.

We can write down a similar argument for the induction step.


---
# References
[[Number Field]]
[[Galois Extensions]]
[[The fundamental theorem of Galois Theory]]
[[Gauss sums]]
[[Number Rings]]
[[Discriminant of an n-tuple]]
