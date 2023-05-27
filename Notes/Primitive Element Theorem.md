202304142304

Type : #Note
Tags : [[Algebra]]

---
# Primitive Element Theorem
### Theorem 1:
```ad-note
title:
Every finite separable extension of a field $K$ is of the form $K(\gamma)$ for some $\gamma$ in the extension.
```
##### Proof:
If $K$ is a finite field, then any finite extension $L$ is a finite field and so, $L ^{\times} = \langle \gamma \rangle$ for some generator $\gamma \in L ^{\times}$. This would give $L = K(\gamma)$.
(Here we used the fact that $L ^{\times}$ is a cylic group for any finite field $L$. For proof see [[Finite Fields]].)

Now when $K$ is infinite, a finite separable extension $L$ is of the form $K(\alpha_{1},\alpha_{2},\dots,\alpha_{n})$ where each $\alpha_{i}$ is separable over $K$.
It suffices to show that when $K(\alpha,\beta)/ K$ is separable then $K(\alpha,\beta) = K(\gamma)$ for some $\gamma$.

Let $L = K(\alpha,\beta)$ and $n = [L:K]$, by Theorem 1 (c) in [[Separable Extensions]], we get that there are $n$ $K-$homomorphisms from $L$ to a field extension $F$ of $K$.
Now we show that $L = K(\alpha + c\beta)$ for some $c$, in fact we will show that this is true for all but finitely many $c$.
Take $K(\alpha+c\beta)$, if it is not equal to $L$, then $[K(\alpha+c\beta) : K] < [L:K]$, and hence it has less than $n$ $K-$homomorphisms from itself to $F$. This means that two of the homomorphisms $\tau,\sigma$ on $L$ are the same on $K(\alpha+c\beta)$. 
This is equivalent to $\sigma(\alpha+c\beta) = \tau(\alpha+c\beta) \implies c =  \frac{\sigma(\alpha) - \tau(\alpha)}{\tau(\beta)-\sigma(\beta)}$. Since there are only finitely many $\sigma,\tau$ pairs, there are only finitely many such $c$. This means for all the other $c$'s, we have $L = K(\alpha+c\beta)$.

###### We can try finding primitive elements for galois extensions.
### Theorem 2:
```ad-note
title:
When $L /K$ is a finite galois extension and $\gamma \in L$, the degree $[K(\gamma):K]$ is the size of the galois orbit of $\gamma$. So $\gamma$ is a primitive element of $L /K$ iff $|\{ \sigma(\gamma) : \sigma \in \mathrm{Gal}(L /K) \}| = [L :K]$.
```
##### Proof:
Since $\gamma$ is separable over $K$, $[K(\gamma) : K]$ is the number of roots of the min poly of $\gamma$ over $K$, which is just the conjugates of $\gamma$ which in turn is just the size of the galois orbit (Theorem 4 [[Galois Correspondence]])

---
# References
[[Field Extensions]]
[[Separable Extensions]]
[[Finite Fields]]
[[Galois Extensions]]
[[Galois Correspondence]]
