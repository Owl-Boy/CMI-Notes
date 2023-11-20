---
tags:
  - Note
  - Incomplete
---
202311071911

Tags : [[Programming Languages]]
# Dependency analysis for letrec expressions
---
A lot of *Haskell* expressions like [[Translation Scheme from Haskell to Lambda Calculus for Some RHS only options#Where Clauses|where clauses]] only produce *let-rec* because of the potential to contain recursive definitions, even though it is possible to write definitions which do not involve recursion. 
Here we analyse definitions that have been converted to *let-rec* form and convert them to nested *let(rec)*

It is desirable to do strictness analysis for the following reasons
- *let* expressions are significantly more efficient to implement than *let-rec*.
- Type Checking may be impossible without it.
- Strictness checking also becomes significantly more efficient.

---
## Example
```haskell
letrec x   = fac z
       fac = \n. IF (= n 0) 1 (* n (fac (- n 1)))
       z   = 4
       sum = \x.\y.IF (= 0 x) y (sum (- x 1) (+ y 1))
in sum x z
```

An equivalent expression would be

```haskell
let 
    z = 4 
in 
	letrec fac  = \n. IF (= n 0) 1 (* n (fac (- n 1)))
in let 
	x = fac z
in letrec 
	sum = \x.\y.IF (= 0 x) y (sum (- x 1) (+ y 1))
in 
	sum x z
```

---
## Dependency Analysis Algorithm
We use the following code as an example for dependency analysis
```haskell
letrec
      a = ...
      b = ... a ...
      c = ... h ... b ... d ...
      d = ... c ...
      f = ... g ... h ... a ...
      g = ... f ...
      h = ... g ...
in
      ...
```
1. For each letrec, we create a graph where the nodes are variables variables bound by *let-rec*. There exists edge $\alpha\to\beta$ iff $\beta$ has a free occurrence in the definition of $\alpha$.
   ![[Pasted image 20231107193044.png]]
2. Existence of loops or cycles would imply that a letrec must be used to deal with the variable defined in said loop/cycle, and we find strongly connected components to get co-dependent variables which need to be put in the same letrec block
3. After quotienting the stronly connected components, we get a *Directed Acyclic Graph*. We can now perform *topo-sort* to get a linear order instead of a tree, that can be converted to the final code, keeping the smallest element in the innermost *let/letrec* block.
    ![[Pasted image 20231107193112.png]]
4. Using that we generate the following code

```haskell
let
     a = ...
in let  
     b = ... a ...
in letrec
     f = ... g ... h ... a
     g = ... f ...
     h = ... g ...
in letrec
     c = ... h ... b ... d ...
     d = ... c ...
in 
     ...
```

---
# References
[[let(rec)-expressions to Ordinary Lambda Calculus]]