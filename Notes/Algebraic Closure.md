202305250905

Type : #Note
Tags : [[Algebra]]

---
# Algebraic Closure
```ad-note
title:
A field $\Omega$ is called **algebraically closed** if it satisfies one of the following equivalent conditions:
1. All nonconstant polynomials in $\Omega[X]$ have a root in $\Omega$.
2. The irreducibles in $\Omega[X]$ are the linear polynomials.
3. All nonconstant polynomials in $\Omega[X]$ split in $\Omega$.
4. Every field of finite degree over $\Omega$ equals $\Omega$.
```
###### Proof that the statements are equivalent:
$(1) \implies (2) \implies (3) \implies (1)$ is trivial.
$(1) \implies (4)$ : A field of finite degree over $\Omega$ contains elements of only finite degree over $\Omega$. Take such an element $\alpha$, and its minimal poly over $\Omega$, call it $f$. $f$ has a root in $\Omega$ by (1), but $f$ is irreducible hence it must be linear, and so $\alpha \in \Omega$.

$(4) \implies (1)$ Take a non constant poly $f$, take the extension $\Omega/(f) = \Omega$ by (4). Then $deg(f) = [\Omega /(f) : \Omega] = 1$
And so $f$ has a root in $\Omega$.

### Theorem:
```ad-note
title:
If $\Omega$ is algebraic over $F$ and every polynomial $f \in F[X]$ splits in $\Omega[X]$, then $\Omega$ is algebraically closed. 
```
###### Proof:
Take a polynomial $f = a_{0} + a_{1}x + \dots a_{n}x ^{n} \in \Omega[X]$. Take a root $\alpha$ of $f$ in an extension $\Omega'$ of $\Omega$.
$$
F \subset F[a_{0},a_{1},\dots a_{n}] \subset F[a_{0},a_{1},\dots a_{n}][\alpha]
$$
Since each extension is finite, each extension is algebraic and hence $\alpha$ is algebraic over $F$.
So there is a poly $g \in F[X]$ with $g(\alpha) = 0$.
But $g$ splits in $\Omega[X]$ hence $\alpha \in \Omega$. Thus, all roots of $f$ are in $\Omega$, hence $f$ splits in $\Omega$, so $\Omega$ is algebraically closed.

---
### Definition:
```ad-note
title: Algebraic closure
1. Let $F$ be a field and $\Omega$ an integral domain containing $F$ as a subring.
Then $$ \bar{F} := \{\alpha \in \Omega \ |\  \alpha \text{ algebraic over } F\} $$
is a field called the _algebraic closure of $F$ in $\Omega$_.

2. A field $\Omega$ is an _algebraic closure_ of a subfield $F$ if it is algebraic over $F$ and is algebraically closed.
```

### Theorem:
```ad-note
title:
Let $\Omega$ be an algebraically closed field. For any subfield $F$ of $\Omega$, the algebraic closure $E$ of $F$ in $\Omega$ is an algebraic closure of $F$.
```
###### Proof:
$E$ is algebraic over $F$ by definition. Now take a poly over $F$, we want to show it splits in $E$.
This poly obviously splits in $\Omega$, since it is algebraically closed. But the roots all belong to $E$ by definition of $E$, hence it splits in $E$.

---
# References
[[Algebraic Extension]]
