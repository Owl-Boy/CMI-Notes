202304011704

Type : #Note
Tags : [[Lambda Calculus]]

---
# Functions Computable in Lambda Calculus
Computability in $\lambda-$calculus is generally defined by the set of function of the type $\mathbb N^{k}\to\mathbb N$

```ad-info
title: Recursive Functions
This is a set of functions which was defined by Dedikendm, Skolem, Gödel, Kleen, etc. and this is equivalent to the set of functions computable by [[Turing Machines]].
```
$f:\mathbb N^{k}\to \mathbb N$ is obtained by composition of function $g:\mathbb N^{l}\to\mathbb N$ and functions $h_1,h_2\dots h_{l}:\mathbb N^{k}\to \mathbb N$ if
$$
f(\vec n)=g(h_{1}(\vec n), h_{2}(\vec n)\dots h_{l}(\vec n))
$$
and the notation for composition is 
$$
f=g\circ(h_{1}, h_{2},\dots h_{l})
$$
$f:\mathbb N^{k} \to \mathbb N$ is obtained by [[Primitive Recursion]] or by [[Mu-Recursion]]

The class of _Primitive Recursive Functions_ is the set of functions where
The initial set of functions that is allowed to be used is 
+ Zero Function - $Z(n)=0$
+ Successor Function - $S(n)=n+1$
+ Projection Function - $\Pi_{i}^{k} (n_{1}\dots n_{k})= n_{i}$
Which is closed under composition and primitive recursion
The class of _Recursive Functions_ is the set of functions preverved under composition, primitive recursion and minimization, and have the initial functions.



---
# References
