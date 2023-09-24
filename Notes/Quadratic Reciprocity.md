202305271605

Type : #Note
Tags : [[Number Theory]] 

---
# Quadratic Reciprocity
```ad-note
title:
Given two odd primes $p,q$, $$
\left(\frac{q}{p}\right)\left(\frac{p}{q}\right) = (-1)^{((p-1)/2)((q-1)/2)}
$$
```

### Proof 1:
Let $\chi$ be a character of order $2$ on $\mathbb{F}_{p}$.
Then by Corollary 1 to Theorem 3 in [[Jacobi Sums]], $$
g(\chi)^{q+1} = \chi(-1)pJ(\chi,\chi, \dots , \chi)
$$
Where there are $q$ $\chi's$ in the right hand side of the equation.
This gives $$
J(\chi,\chi, \dots ,\chi) = p ^{-1}(g(\chi)^{2})^{(q+1)/2}\chi(-1)=p ^{-1}(p \chi(-1))^{(q+1)/2} \chi(-1) = p ^{(q-1)/2}(-1)^{((p-1)/2)((q-1)/2)}
$$
Now $J(\chi,\chi, \dots,\chi) = \sum\chi(t_{1})\chi(t_{2})\dots \chi(t_{q})$.
If $t_{1} = t_{2} = \dots = t_{q} = \frac{1}{q}$, we get $\chi\left( \frac{1}{q} \right)^{q} = \chi(q)^{-q} = \chi(q) = \left(\frac{q}{p}\right)$.
When not all $t_{i}$ are equal, we can cyclicly rotate them to get $q$ equal terms, and so, mod q they vanish.

Thus $$\begin{align}
J(\chi, \dots ,\chi) &= \left( \frac{q}{p} \right) \ (\mathrm{mo d} \ q) \\
&= p ^{(q-1)/2}(-1)^{((p-1)/2)((q-1)/2)} (\mathrm{mo d} \ q) \\
\implies \left( \frac{q}{p} \right) \left( \frac{p}{q} \right) &= (-1)^{((p-1)/2)((q-1)/2)} (\mathrm{mo d} \ q)
\end{align}
$$
and hence, we can drop the mod q since both sides are absolute value 1.


---
# References
[[Legendre Symbol]]
[[Multiplicative Characters]]
[[Jacobi Sums]]
[[Equations over Finite Fields]]
