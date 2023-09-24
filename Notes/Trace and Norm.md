202306021206

Type : #Note
Tags : [[Number Theory]]

---
# Trace and Norm
```ad-note
title:
Let $K$ be a number field of degree $n$, we define two function $T ^{K}$ and $N ^{K}$ on $K$ as follows: Let $\sigma_{1},\sigma_{2}, \dots,\sigma_{n}$ be the $n$ embeddings of $K$ into $\mathbb{C}$.
For each $\alpha \in K$, set $$
\begin{align}
T^K(\alpha) = \sum_{i=1}^{n}\sigma_{i}(\alpha)  \\
N^K(\alpha) = \prod_{i=1}^{n}\sigma_{i}(\alpha)
\end{align}
$$
```
- Write $T,N$ instead of $T ^{K}, N ^{K}$ if context is clear.
- $T(\alpha+\beta) = T(\alpha) + T(\beta)$
- $N(\alpha\beta) = N(\alpha)N(\beta)$
- For $r \in \mathbb{Q}$, $T(r) = nr$, $N(r) = r ^{n}$.
- For $r \in \mathbb{Q}, \alpha \in K$ $T(r\alpha)= rT(\alpha)$, $N(r\alpha) = r ^{n} N(\alpha)$

### Theorem 1:
```ad-note
title:
Let $\alpha$ have degree $d$ over $\mathbb{Q}$. Let $t(\alpha), n(\alpha)$ denote the sum and product of its conjugates respectively.
Then 
$$
\begin{align}
T(\alpha) = \frac{n}{d}t(\alpha) \\
N(\alpha) = (n(\alpha))^{n/d}
\end{align}
$$

where $n = [K:\mathbb{Q}]$.
```
###### Proof:
Every embedding of $\mathbb{Q}(\alpha)$ into $\mathbb{C}$ extends to $\frac{n}{d}$ embeddings of $K$ into $\mathbb{C}$. (refer to [[Number Field]])

### Corollary 1:
```ad-note
title:
$T(\alpha),N(\alpha) \in \mathbb{Q}$
```
###### Proof:
$t(\alpha),n(\alpha) \in \mathbb{Q}$ since they are coefficients of $\alpha's$ minimal polynomial, and the result follows.

### Corollary 2:
```ad-note
title:
If $\alpha$ is an algebraic integer, $T(\alpha),N(\alpha) \in \mathbb{Z}$.
```

--- 
# Generalisations
```ad-note
title:
Let $K,L$ be number fields with $K \subset L$. Denote by $\sigma_{1},\sigma_{2},\dots,\sigma_{n}$ the $n$ embeddings of $L$ in $\mathbb{C}$ which fix $K$ pointwise. Here $n = [K:L]$.
For $\alpha \in L$, the relative trace and relative norm are defined by:
$$
\begin{align}
T ^{L}_{K}(\alpha) = \sum_{i=1}^{n}\sigma_{i}(\alpha) \\
N ^{L}_{K}(\alpha) = \prod_{i=1}^{n}\sigma_{i}(\alpha)
\end{align}
$$
```
- $T ^{L}_{K}(\alpha+\beta) = T ^{L}_{K}(\alpha) + T ^{L}_{K}(\beta)$
- $N ^{L}_{K}(\alpha\beta) = N ^{L}_{K}(\alpha)N ^{L}_{K}(\beta)$
- For $r \in K$, $T ^{L}_{K}(r) = nr$, $N ^{L}_{K}(r) = r ^{n}$.
- For $r \in K, \alpha \in L$ $T_{K}^{L}(r\alpha)= rT_{K}^{L}(\alpha)$, $N ^{L}_{K}(r\alpha) = r ^{n} N ^{L}_{K}(\alpha)$

### Theorem 2:
```ad-note
title:
Let $\alpha$ have degree $d$ over $K$. Let $t(\alpha), n(\alpha)$ denote the sum and product of its conjugates over $K$ respectively.
Then 
$$
\begin{align}
T^L_K(\alpha) = \frac{n}{d}t(\alpha) \\
N^L_K(\alpha) = (n(\alpha))^{n/d}
\end{align}
$$

where $n = [K:\mathbb{Q}]$.
```
###### Proof:
Every embedding of $\mathbb{Q}(\alpha)$ into $\mathbb{C}$ extends to $\frac{n}{d}$ embeddings of $K$ into $\mathbb{C}$. (refer to [[Number Field]])

### Corollary:
```ad-note
title:
$T_{K}^{L}(\alpha)$ and $N_{K}^{L}(\alpha)$ are in $K$. If $\alpha \in \overline{\mathbb{Z}} \cap L$ then they are in $\overline{\mathbb{Z}} \cap K$.
```

### Theorem 3:
```ad-note
title:
Let $K,L,M$ be number fields with $K \subset L \subset M$. Then for all $\alpha \in M$, we have $$
\begin{align}
T_{K}^{L}(T_{L}^{M}(\alpha)) = T_{K}^{M}(\alpha)\\
N_{K}^{L}(N_{L}^{M}(\alpha)) = N_{K}^{M}(\alpha)
\end{align}
$$
```
###### Proof:
Let $\sigma_{1},\dots,\sigma_{n}$ and $\tau_{1},\dots,\tau_{m}$ be the embeddings of $L$ and $M$ which fix $K$ and $L$ pointwise, respectively.
Now we want to compose the $\sigma'$s with the $\tau'$s but for that we need to extend them to a normal extension $N$ of $M$. So choose any extension of each $\sigma_{i}$ and $\tau_j$, and relabel those automorphisms of $N$ as $\sigma_{i}$ and $\tau_{j}$.

Now, $$
\begin{align}
T_{K}^{L}(T_{L}^{M}(\alpha)) = T_{K}^{L}\left( \sum_{i=1}^{m}\tau_{i}(\alpha) \right) &= \sum_{j=1}^{n}\sigma_{j}\left( \sum_{i=1}^{m}\tau_{i}(\alpha) \right)  \\
&= \sum_{i,j} \sigma_{j}(\tau_{i}(\alpha)) \\
\end{align}
$$
Now note that each $\sigma_{j}\circ \tau_{i}$ is an embedding of $M$ which fixes $K$.
We know that there are $mn$ embeddings of $M$ fixing $K$, if we can show that the $\sigma_{i} \circ \tau_{j}'s$ are distinct, we will be done.
If $\sigma_{i}\circ\tau_{j} = \sigma_{k}\circ\tau_{\ell}$, then applying both sides to an element of $L$, we get $\sigma_{i}=\sigma_{k}$ are equal on the image of $L$ under the embeddings $\tau_{j},\tau_{\ell}$. This gives $i = k$.
Since $\sigma_{i}=\sigma_{k}$ is an automorphism, we can multiply by its inverse to get $\tau_{j} = \tau_{\ell}$, and hence $j = \ell$.



---
# References
[[Algebraic Integers]]
[[Number Field]]

