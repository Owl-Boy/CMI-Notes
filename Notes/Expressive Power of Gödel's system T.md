202307261607

Type : #Note
Tags : [[Type Theory]]

---
# Expressive Power of Gödel's system T
### Booleans
The typical example is given by the logical connectors
$$
\begin{matrix}\neg u=\text {D F T}\ u & \text{disj $(u, v)=$ D T}\ u\ v & \text{conj$(u,v)=$ D $v$ F $u$} \end{matrix}
$$
Here $\text{disj}(u,\text T)$ does not simplify to $\text T$. hence the definition is not symmetric
It is in fact not possible to make a symmetric form of disjunction which, i.e. we cannot create a $G$ such that 
$$
\begin{matrix}G\langle \text T, x\rangle \rightsquigarrow \text T & G\langle x, \text T\rangle\rightsquigarrow \text T & G\langle\text {F,F}\rangle\rightsquigarrow\text F\end{matrix}
$$

### Integers
obviously $\overline n=\text S^{n}\text O$ represents the integers, and then we can define addition and other functions for these terms like [[Church Numerals|lambda calculus]]. 
example
$$
\text{null}(x)=\text{R T }(\lambda z^{\text{Bool}}.\lambda z'^{\text{Int}}.\text F) x
$$
To define Addition we have 
$$t[x,y]\rightsquigarrow\text R\ x\ (\lambda z^{\text {Int}}.\lambda z'^{\text{Int}}.\text S\ z)\ y$$

Note that these examples make serious use of higher types.

We can also define iterator in the following way

$\text{it}(f) x=\text R\ \overline1(\lambda z^{\text{Int}}.z'^{\text{Int}}.f\ z)x$
where $f:\text {Int}\to\text{Int}$ which gives $\text{it}$ the type $(\text{Int}\to\text{Int})\to(\text{Int}\to\text{Int})$ and $\text{it}(f)x:= f^{x}\left(\overline 1\right)$

```ad-info
title:Ackerman's function in System T
Functions like Ackerman's function is also easily definable as we can have recursive function of complex types like $\text{Int}\to\text{Int}$ .
$$
A := \lambda m.\;\;\; \text R\;\;\;\; \text S\;\;\;\; (\lambda z.\lambda z'. (\lambda n. \text{it}(z)n))\;\;\;\; m
$$
```

Iterators an be used to make the recursion function.
To do so, modify the iterator to make it take more kinds of inputs

$$
\begin{align*}
I &: (U\to U) \to \text{Int}\to(U\to U)\\
I\ f\ p\ i&: \text R\ i\ (\lambda z.\lambda z'. f\ z)\ p
\end{align*}
$$

The big difference being that we can also use the "level" of the recursion in the function, the generalization allows us to do that, we can now define recursion in the following way
$$
R\ u\ v\ t = \text I\ v'\ t\ \langle u,\text O\rangle 
$$
where $v' \langle a,b \rangle = v\ a\ b$

---
# References
[[Result of Expressive Power of Gödel's system T]]