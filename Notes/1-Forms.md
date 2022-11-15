202210310910

Type : #Note
Tags : [[Calc]]

---
# 1-Forms
A _k-form_ is a map $w: U \to \Lambda^k V$ , the degree of such a $w$ is $k$, one forms are particularly important.

Given a k-form $\omega$ and a l-form $\eta$ , they can be multiplied to get the k+l-form $\omega\wedge\eta$
$$
[\omega\wedge\eta](p) \equiv_{def} \omega(p)\wedge\eta(p)
$$
Given a function $f$ on $U$, we define its exterior derivative $df$ to be the 1-form defined by $df (p) [u] = D f(p)[u]$  which is the directional derivative of $f$ at $p$ along the vector $u$.

_Claim:_
$$
df = \sum_i{\partial f \over \partial x^i}dx^i
$$
_Proof:_
$$
Df(p)[u] = \sum_i{\partial f\over\partial x^i}dx^i(p)[u]=\sum_i{\partial f\over\partial x^i}(p)\phi_i(u)
$$

This also gives
$$
Df(p)[e_i]={\partial f\over \partial x^i}(p)[e_i]
$$
This also shows that it is $C^\infty$ as it is a sum of the form in which all the terms are $C^\infty$, which are a function multiplied by a constant 1-form.
$$
df =\sum_i{\partial f \over\partial x^i}\phi_i 
$$


 
---
# Related Problems

---
# References
