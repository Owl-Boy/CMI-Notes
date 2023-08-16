202307261607

Type : #Note
Tags : [[Type Theory]]

---
# Gödel's system T
The extremely rudimentary type system we have studied has very little expressive power. We can represent integers and booleans, but not sufficiently many functions. So systems such as that of Gödel appear.

```ad-info
title:
Systems like **T** area step backwards from the logical viewpoint: the new schemes do not correspond to proofs in an extended logical system. In particular, that makes it difficult to stidy them.
```
[[Gödel's system F]] resolves the problems in satisfying manner.

### The Calculus
#### The Types
The following types are present in the calculus
- Atomic Types represented by : $A,B,\dots$
- Product Types such as $A\times B,\dots$
- Arrow Types which represent functions : $A\to B$
- Constant Types $\text{Int}$ and $\text{Bool}$

### Terms
Besides the usual 5 of Simply types lambda calculus, there are schemes for specific constants $\text{Int}$ and $\text{Bool}$.

1. $\text{Int}$-Introduction
	1. $O$ is a constant type $Int$.
	2. if $t$ of type $Int$, then $S\ t$ is of type $\text{Int}$
2. $\text{Int}$-elimination
	1. If $u, v, t$ have the types $U, U\to{\text{Int}\to U}, \text{Int}$, then $\text R\ u\ v\ t$ is of the type $U$
3. $\text{Bool}$-Introduction
	1. $\text{T}$ and $\text{F}$ are constants of type $\text{Bool}$
4. $\text{Bool}$-Reduction
	1. if $u,v,t$ are of the types $U,U,\text{Bool}$ then $\text D\ u\ v\ t$ is of the type $U$

The intended types of these terms are
1. $\text O$ represents 0 and $\text S$ is the successor function
2. $\text R$ is the recursion operator
3. $\text T$ and $\text F$ are truth values
4. $\text D$ is the "If..Then..Else" operator

### Conversions
To the classical redexes we add:
$$
\begin{matrix} \text{R}\ u\ v\ \text{O}\rightsquigarrow u & \text D\ u\ v\ \text{T}\rightsquigarrow u \\ \text R\ u\ v\ (\text S\ t)\rightsquigarrow v\ (\text R\ u\ v\ t)\ t & \text D\ u\ v\ \text F \rightsquigarrow v \end{matrix}
$$

---
# References
[[Normalization Theorem for Gödel's system T]]