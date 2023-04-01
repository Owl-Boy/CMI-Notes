202303302303

Type : #Note
Tags : [[Topology]]

---
# Tietze Extension Theorem
```ad-note
title:
Let $X$ be a normal space, let $A \subseteq X$ be a closed subspace, and let $f:A \to [a,b]$ be a cts function for some $[a,b] \subseteq \mathbb{R}$. There exists a cts function $\bar{f}:X \to [a,b]$ such that $\bar{f}|_{A} = f$.
```

### Lemma:
```ad-note
title:
Let $X$ be a normal space, $A \subseteq X$ be a closed subspace, and let $f : A \to \mathbb{R}$ be a cts function such that for some $C > 0$ we have $|f(x)| \le C$ for all $x \in A$. There exists a cts function $g : X \to \mathbb{R}$ such that $|g(x)| \le \frac{1}{3}C$ for all $x \in X$ and $|f(x) - g(x)| \le \frac{2}{3}C$ for all $x \in A$.
```

##### Proof:
Take $Y = f ^{-1}\left( \left[ -C,-\frac{C}{3} \right] \right), Z = f ^{-1}\left( \left[ \frac{C}{3}, C \right] \right)$. Since $f : A \to \mathbb{R}$ is a cts function, these are closed subsets of $A$ and hence of $X$. So by Urysohn's Lemma,  there is a function $h : X \to \mathbb{R}$ such that $h(Y) \subset \{ 0 \}, h(Z) \subset \{ 1 \}$.
Then take the function $g(x) = \frac{2C}{3}\left( h(x)-\frac{1}{2} \right)$.
Then for $x$ in each of $Y,Z,X \setminus (Y \cup Z)$, we get that $f(x),g(x)$ belong to the same interval $\left[ -C,-\frac{C}{3} \right]$, $\left[ \frac{C}{3},C \right]$, $\left[ -\frac{C}{3}, \frac{C}{3} \right]$.
Hence done.

##### Proof of Tietze's theorem:
WLOG take $[a,b] = [0,1]$
We construct a sequence of functions $g_{n} : X \to [0,1]$ such that 
1) $\displaystyle |g_{n}(x)| \le \frac{1}{3}\left( \frac{2}{3} \right)^{n-1}$
2) $\displaystyle |f(x) - \sum \limits_{ i=1}^{ n }g_{i}(x)| \le \left( \frac{2}{3} \right)^{n}$ for all $x \in A$.

This follows by induction and the previous lemma.
Then take $\bar{f} := \sum \limits_{ i=1}^{ \infty }g_{i}(x)$. This is uniformly converging because of condition $(1)$. And $\bar{f}|_{A} = f$ because of condition $(2)$.

---
### Another formulation of Tietze's Theorem
```ad-note
title:
Let $X$ be a normal space, let $A \subset X$ be a closed subset, and let $f : A \to \mathbb{R}$ be a cts function. There exists a cts function $\bar{f} : X \to \mathbb{R}$ such that $\bar{f}|_{A} = f$.
```
##### Proof:
It is enough to show that for any cts function $f : A \to (-1,1)$, there is a cts function $\bar{f} : X \to (-1,1)$ since $(-1,1)$ is homeomorphic to $\mathbb{R}$.

Assume then $f:A \to (-1,1)$ is cts, then by Tietze's theorem, there is $f' : A \to [-1,1]$ cts.
Let $B = f' ^{-1}(\{ -1,1 \})$. The set $B$ is closed in $X$, disjoint from $A$, hence by Urysohn's lemma, there is a function $k : X \to [0,1]$ such that $k(B) \subset \{ 0 \}$, and $k(A)\subset \{ 1 \}$.
Then define $\bar{f} := k(x)\cdot f'(x)$. This is the required function.

---
# References
[[Urysohn Lemma]]
[[Continuous Functions]]
[[Closed sets]]
[[Subspace Topology]]
[[Normal Spaces]]

