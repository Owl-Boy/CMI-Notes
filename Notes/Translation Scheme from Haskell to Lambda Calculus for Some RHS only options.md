---
tags:
  - Note
  - Incomplete
---
202310222010

Tags : [[Programming Languages]]

---
# Translation Scheme from Haskell to Lambda Calculus for Some RHS only options

## For More Complex Definitions
*Haskell* has some more options that can be used to simplify the syntax of the definition by adding things like **Conditional Equations** and **Where Clauses**.
These things combine with **Pattern matching** but only affect the Right side of the definition, hence we define [[Translation Scheme from Haskell to Lambda Calculus for Some RHS only options|TR]]
to only deal with the right hand side of the definition.

Considering that the following modification is required to define $\mathbf{TD}$
$$
\mathbf{TD}\textlbrackdbl\;p=R\;\textrbrackdbl\quad\equiv\quad\mathbf{TE}\textlbrackdbl\;p\;\textrbrackdbl=\mathbf{TR}\textlbrackdbl\;R\;\textrbrackdbl
$$

---
## Conditional Equations
Consider the following definition
```haskell
gcd a b | a > b  = gcd (a-b) b
        | a < b  = gcd a (b-a)
        | a == b = a
```
It is easy to see that the translation of the part after the `|` would be
```scheme
(IF (>  a b) (gcd (- a b) b)
(IF (<  a b) (gcd a (- b a))
(IF (== a b) a FAIL)))
```
Note that if all the guards fail, `FAIL` is returned, we can optimize to ignore that case if the final condition is the constant `True`.

This can be summarized by 
![[Pasted image 20231022194702.png]]

---
## Where Clauses
*Haskell* allows the right side of the definition to be qualified by a $\text{Where}$ clause. Like
```haskell
gcd a b | a > b  = gcd diff b
        | a < b  = gcd a (-diff)
        | a == b = a
    where
	     diff = a - b
```
$\text{where-}$clauses is very similar to $\text{let-}$expressions, the only difference being that $\text{where-}$clauses provide a nice syntactic sugar over $\text{let-}$expressions when used with conditional definitions
The obvious translation would be
```haskell
gcd a b = 
    letrec
	    diff = a - b
	in
		if (a < b)  then gcd diff b else
		if (a > b)  then gcd a (-diff) else
		if (a == b) then a else FAIL
```

---
## Summary
![[Pasted image 20231022201227.png]] ^d83623


---
# References
[[Translation Scheme from Haskell to Lambda Calculus for Expressions]]
[[Translation Scheme from Haskell to Lambda Calculus for Some RHS only options]]
[[Translating Haskell Programs to Lambda Calculus]]