---
tags:
  - Note
  - Incomplete
---
202311051311

Tags : [[Programming Languages]], [[Lambda Calculus]]
# Converting Enriched Lambda Calculus to Ordinary Lambda Calculus
---
After [[Translating Haskell Programs to Lambda Calculus]] with features like pattern matching lambda abstractions, let/letrec-expressions, case statements and then $\triangleright$ operator, for each situation we can give a conversion from [[Enriched Lambda Calculus]] to [[Lambda Calculus Introduction|Lambda Calculus]].

## Pattern Matching
Converting Pattern matching to *Ordinary lambda Calculus* can be summed up as 
![[Pattern Matching to Ordinary Lambda Calculus#^1331d9]]

---
## let/letrec-expressions
Converting *Let/Letrec*-expressions is bit more involved than the others, and is discussed in detail in [[let(rec)-expressions to Ordinary Lambda Calculus]]

It is a multi step process whose plan can be given by
![[let(rec)-expressions to Ordinary Lambda Calculus#^aa141c]]

---
## Case Statements
Converting *Case-expressions* to lambda calculus can be summaries in the following way
![[Pasted image 20231105150419.png]]
for product type and 
![[Pasted image 20231105150444.png]]
for sum-types.
This is discussed in more depth in [[Converting Case Expressions to Ordinary Lambda Calculus]]

---
## $\triangleright$ and $\text{FAIL}$
The above two expressions can be directly encoded in Lambda Calculus by adding them as Built-in Constants and having 

$$
E_{1}\; \triangleright\;E_{2}\quad\equiv\quad\text{FATBAR}\;\;E_{1}\;\;E_{2}
$$
Although we can also get rid of most of them as discussed in [[Optimisations for Expressions containing FAIL and I>]].

---
# References
- [[Pattern Matching to Ordinary Lambda Calculus]]
- [[Converting Case Expressions to Ordinary Lambda Calculus]]
- [[let(rec)-expressions to Ordinary Lambda Calculus]]