202308181008

Type : #Note
Tags : [[Algebraic Graph Theory]]

---
# Primitive Transitive Permutation Group

```ad-info
title:
If the only blocks of Transitive permutation group are trivial, then it called **Primitive**.
```

_Lemma:_ If $(\Gamma,X)$ is $2-$transitive, then it is primitive
_Proof:_ consider a block $B$, if it is non trivial, then $\exists x, y\in B$ and $\exists z\notin B$, then consider $\sigma: (x, y)\to (x, z)$. This is a contradiction.

### Theorem
Let $(\Gamma, X)$ be transitive, then $(\Gamma, X)$ is primitive iff $\forall x\in X,\Gamma_{x}$ is a maximal subgroup of $\Gamma$.
### Proof
Show that the following are equivalent
1. $\Gamma_{x}$ is not minimal.
2. $\exists$ a non trivial block
(1. $\implies$ 2.)
$\exists H$ such that $\Gamma_{x}\subsetneq H\subsetneq\Gamma$ 
And let $B$ be the orbit of $H$ which contains $x$
If $B$ is a singleton, then $\Gamma_{x}=H$
If $B=X$ 
then consider some $\alpha\in\Gamma$ such that $\alpha(x)=z$, but since $z$ is in the orbit of $H$, we have $\beta$ such that $\beta(x)=z$, and we have $\beta^{-1}\circ\alpha(x)=x\in H$ hence $\alpha\in H$ which implies $H=\gamma$
which is also a contradiction.

(2. $\implies$ 1.)

$\Gamma_{B}=\{\sigma\in\Gamma:\sigma(B)=B\}$
then let $H=\Gamma_{B}$. then $\Gamma_{x}\subseteq H\subseteq \Gamma$. We show that $H\ne \Gamma_{x}$ and $H\ne\Gamma$
$H\ne\Gamma_{x}$ : consider $y\in B\ne H$. then $y\in B\cap\sigma (B)$ then $\sigma\in H$. such a $\sigma$ exists because of transitivity.

Suppose $H=\Gamma$ proof equivalent to the proof in the first part.





---
# References
