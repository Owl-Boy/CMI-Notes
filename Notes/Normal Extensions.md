202304161204

Type : #Note
Tags :[[Algebra]]

---
# Normal Extensions
```ad-note
title:
A field extension $L/K$ is called _normal_ if every irreducible poly in $K[X]$ that has a root in $L$ splits completely in $L[X]$.
```

### Theorem 1:
```ad-note
title:
If $|\mathrm{Aut}(L /K)| = [L : K]$ then $L/K$ is normal
```
##### Proof:
Look at Theorem 4 in [[Galois Correspondence]] for a proof.

### Theorem 2:
```ad-note
title:
The splitting field of a separable polynomial is a normal extension.
```
##### Proof:
This is just theorem 3 in [[Galois Correspondence]] followed by an application of theorem 1 above.

### Theorem 3:
```ad-note
title:
For a finite extension $L/K$, TFAE:
1) $L/K$ is normal
2) $L$ is the splitting field over $K$ of a polynomial in $K[X]$
```
##### Proof:
(1) $\implies$(2)
Write $L = K(\alpha_{1},\alpha_{2},\dots,\alpha_{n})$, take the minimal polynomial of all the $\alpha_{i}$'s, and take their product (get rid of repeated factors in the product). Now $L$ is the splitting field of this polynomial over $K$.

(2) $\implies$ (1)
There is a poly $f(X) \in K[X]$ s.t. $L$ is a splitting field of $f$ over $K$.
Let $f(X) = (X-\beta_{1})(X-\beta_{2})\dots(X-\beta_{n})$, then any $\alpha \in L$ is of the form $g(\beta_{1},\beta_{2},\dots,\beta_{n})$ for some polynomial $g \in K[X_{1},X_{2},\dots,X_{n}]$. 
Consider 
$$
h(X) = \prod \limits_{ \sigma \in S_{n}} (X - g(\beta_{\sigma(1)},\beta_{\sigma(2)}\dots,\beta_{\sigma(n)}))
$$
Now $\alpha$ is a root of $h$. Hence its min poly $\pi_{\alpha} | h$. But the coefficients of $h$ are symmetric polys in the $\beta_{i}$'s, hence they are polynomials in the elementary symmetric polynomials of the $\beta_{i}$'s which are just coefficients of $f$, and hence elements of $K$. Thus the coefficients of $h$ are in $K$. Hence $h$ is a poly over $K$ that splits in $L$, hence $\pi_{\alpha}$ splits in $L$.


---
# Examples
1. Any quadratic extension is normal.
2. 

---
# References
[[Galois Correspondence]]
[[Extension Field]]
[[Splitting Fields]]


