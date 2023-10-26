---
tags:
  - Note
  - Incomplete
---
202310210410

Tags : [[Programming Languages]]

---
# Translation Scheme from Haskell to Lambda Calculus for Definitions

The $\mathbf{TD}$ scheme takes a *Haskell* definition as its argument and produces a $\text{letrec}$ definition as its result.

## Variable Definition
Consider the following definition
```haskell
v = 5 * 7
```
which can be translated to 
```haskell
v = * 5 7
```

In general we get
$$
\mathbf{TD}\textlbrackdbl\;v=E\;\textrbrackdbl\quad\equiv\quad v=\mathbf{TE}\textlbrackdbl\;E\;\textrbrackdbl
$$
where $v$ is a variable and $E$ is an expression.

---
## Simple Function Definition
Consider the following definition
```haskell
square n = n * n
```
which translates to 
```haskell
square = \n. * n n
```

We can generalize this as follows
$$
\mathbf{TD}\textlbrackdbl\;f\;v_{1}\;\dots\;v_{n}=E\;\textrbrackdbl\quad\equiv\quad
f=\lambda v_{1}\dots\lambda v_{n}.\mathbf{TE}\textlbrackdbl\; E\;\textrbrackdbl
$$
---
## Function Definitions with Pattern  Matching
Consider the following definition
```haskell
head [x:_] = x
```
It is not plausible to translate us using the [[Translation Scheme from Haskell to Lambda Calculus for Definitions#Simple Function Definition|above rule]] but the syntax of pattern matching is a subset of expressions, so we can do the following.
$$
\mathbf{TD}\textlbrackdbl\;f\;p_{1}\dots p_{n}=E\;\textrbrackdbl\quad\equiv\quad f=\lambda v_{1}\dots\lambda v_{n}.(((\lambda p_{1}'\ \dots\lambda p_{n}'. E')v_{1}\dots v_{n}) \triangleright \text{ERROR})
$$

More in-depth analysis of the following topics is done in [[Patterns]].

---
![[Translation Scheme from Haskell to Lambda Calculus for Some RHS only options#For More Complex Definitions]]

---
## Summary
![[Pasted image 20231022202606.png]]


^ab1963
---
# References
[[Translation Scheme from Haskell to Lambda Calculus for Definitions]]
[[Translation Scheme from Haskell to Lambda Calculus for Some RHS only options]]
[[Translating Haskell Programs to Lambda Calculus]]