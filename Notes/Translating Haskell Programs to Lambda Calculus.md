---
tags:
  - Note
  - Incomplete
---
202310210310

Tags : [[Programming Languages]]

---
# Translating Haskell Programs to Lambda Calculus
A *Haskell* program can be consists of a set of definitions with an expression to be evaluated. 
I will layout haskell programs in the following way to keep the components separate
```
set of definitions
---
Expressions to be evaluated
```
for example 
```haskell
square n = n * n
---
2 * (square 5)
```
and the translation to [[Enriched Lambda Calculus]] will be
```ocaml
let square = \n. * n n
in  (* 2 (square 5))
```
---
To help describe the process, we talk about two translation schemes, one for the final expression called [[Translation Scheme from Haskell to Lambda Calculus for Expressions|TE]] and one for all the definitions called [[Translation Scheme from Haskell to Lambda Calculus for Definitions|TD]]. We also make [[Translation Scheme from Haskell to Lambda Calculus for Some RHS only options|TR]] to talk about more complicated right hand side only features of the language.

These can be summarized as
![[Translation Scheme from Haskell to Lambda Calculus for Expressions#^76f158]]
![[Translation Scheme from Haskell to Lambda Calculus for Definitions#^ab1963]]
![[Translation Scheme from Haskell to Lambda Calculus for Some RHS only options#^d83623]]
---

With these, given a *Haskell program*
```
Definition 1
Definition 2
...
Definition n
---
Expression
```
we generate the following lambda expression
```
letrec 
    TD[[ Definition 1 ]]
    TD[[ Definition 2 ]]
    ...
    TD[[ Definition n ]]
in 
    TE[[  Expression  ]]
```

`let` was used in the previous example instead of `letrec`, but *Haskell* programs can have recursive definitions, so we use `letrec` in general. 

---
## Example
```haskell
average a b = (a+b)/2
---
average 2 (3+5)
```

This will be transformed to
```
letrec
    TD[[ average a b = (a+b)/2 ]]
in
	TE[[ average 2 (3+5) ]]
```

The application for `TE` gives us
```
   TE[[ average 2 (3+5)]]
-> TE[[ average ]]  TE[[ 2 ]] TE[[ 3+5 ]]
-> average 2 (TE[[ + ]] TE[[ 3 ]] TE[[ 5 ]] )
-> average 2 (+ 3 5)
```

Similarly, application of `TD` gives us
```
   TD[[ average a b = (a+b)/2 ]]
-> average = \a.\b. TE[[ (a+b)/2 ]]
-> average = \a.\b.( TE[[ / ]] TE[[ (a+b) ]] TE[[ 2 ]])
-> average
      = \a.\b.(/ (TE[[ + ]] TE[[ a ]] TE[[ b ]]) 2)
-> average = \a.\b.(/ (+a b) 2)
```

putting it all together we get
```
letrec
    average = \a.\b.(/ (+ a b) 2)
in
	average 2 (+ 3 5)
```

To complete the example, this is the above expression converted to ordinary lambda calculus

$$
(\lambda \text{average}.(\text{average}\; 2\;(+\;3\;5)))\quad(\lambda a.\lambda b.(/ (+\;a\;b)\;2))
$$


```ad-todo
- Defining Types
- Type Checking
```

---
# References
- [[Enriched Lambda Calculus]]
- [[Translation Scheme from Haskell to Lambda Calculus for Expressions]]
- [[Translation Scheme from Haskell to Lambda Calculus for Definitions]]
- [[Translation Scheme from Haskell to Lambda Calculus for Some RHS only options]]
- [[Evaluating Pattern Matching in Lambda Calculus]]