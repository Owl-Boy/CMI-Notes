202306021206

Type : #Note
Tags :[[Number Theory]]

---
# Number Field
```ad-note
title:
A number field is a finite extension of $\mathbb{Q}$.
```
- A number field is an algebraic extension of $\mathbb{Q}$.
- Every such field has the form $\mathbb{Q}[\alpha]$ for some algebraic number $\alpha \in \mathbb{C}$ ([[Primitive Element Theorem]])
- Examples are [[Cyclotomic Fields]].

### Proposition 1:
```ad-note
title:
Let $K$ be a degree $n$ extension of $L$. Then there are exactly $n$ extensions to $K$ of any embedding of $L$ in $\mathbb{C}$.
```
###### Proof:
Consider $\sigma : L \to \mathbb{C}$ an embedding, and let $K = L(\alpha_{1},\alpha_{2},\dots,\alpha_{n})$.
Let $f_{1}$ be the minimal poly of $\alpha_{1}$ over $L$. Now $f_{1}(\alpha_{1}) = 0 \implies (\sigma f_{1})(\sigma\alpha_{1}) = 0 \implies$ $\alpha_{1}$ is sent to a root of $\sigma f_{1}$.
Now any extension of $\sigma$ to $L(\alpha_{1})$ is given by the image of $\alpha_{1}$, there are $deg(\sigma f) = deg(f)$ choices for this. And any choice leads to a valid extension. Thus there are $[L(\alpha_{1}) : L]$ extensions $\widetilde{\sigma}$ of $\sigma$ to $L(\alpha_{1})$.

Putting $L(\alpha_{1},\alpha_{2})$ and $L(\alpha_{1})$ inplace of $L(\alpha_{1})$ and $L$, we get there are $[L(\alpha_{1},\alpha_{2}):L(\alpha_{1})]$ extensions of $\widetilde{\sigma}$ to $L(\alpha_{1},\alpha_{2})$, hence $[L(\alpha_{1},\alpha_{2}):L]$ extensions of $\sigma$ to $L(\alpha_{1},\alpha_{2})$.
Thus, by induction, there are $[K:L]$ extensions of $\sigma$ to $K$.

### Corollary:
```ad-note
title:
There are exactly $n$ embeddings of $K$ in $\mathbb{C}$, given that $[K:\mathbb{Q}] = n$.
```

### Proposition 2:



---
# References
[[Primitive Element Theorem]]
