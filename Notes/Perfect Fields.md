202305251305

Type : #Note
Tags : [[Algebra]]

---
# Perfect Fields
```ad-note:
title:
A field $F$ is **perfect** if it has characteristic zero or it has characteristic $p$ and every element of $F$ is a $p$th power.
```

### Theorem:
```ad-note
title:
A field F is perfect iff every irreducible polynomial in $F[X]$ is separable.
```
###### Proof:
Perfect $\implies$ irreducible is separable.
If $char(F) = 0$, then done.
If $char(F) = p$, then take an unseparable polynomial $f(X) = a_{0} + a_{1}X ^{p} + \dots a_{n} X ^{pn} \in F[X]$.
Since $a_{i} \in F$ and $F$ is perfect, $a_{i} = b_{i} ^{p}$ for some $b_{i} \in F$ for all $i$.
Hence, $f(X) = (b_{0} + b_{1}X + \dots b_{n}X ^{n}) ^{p}$ and hence is not irreducible.

Hence, irreducible implies separable.

Irreducible is separable $\implies$ Perfect.
If char(F) = 0 then done.
If char(F) = p, then suppose that $a \in F$ which is not a $p$th power. 
Then $X ^{p} - a$ is irreducible but not separable.

---
# References
