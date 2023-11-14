---
tags:
  - Note
---
202310251410

Tags : [[Programming Languages]]

---
# Evaluating Pattern Matching in Lambda Calculus

```ad-note
This note is motivation for the solution: [[Match Function for Enriched Lambda Calculus]].
```

## Intuitive Approach
Consider the following example
```haskell
zipWith f []     ys     = []
zipWith f (x:xs) []     = []
zipWith f (x:xs) (y:ys) = f x y : zipWith f xs ys
```
This function, takes in `f` and two lists as arguments and there is non-trivial pattern matching on the two lists.

Given the inputs, the intuitive way that one should proceed with pattern matching goes as follows
1. the function is always pattern matched 
2. we check if the list 1 is empty, if it is, then second list is pattern matched and we return an empty list
3. If it fails we move to the next step, 
	1. match `f`
	2. we then check if the first list is non empty, if it is we check if the second list is empty
	3. If successful we return empty
4. If either of those fail then we move to the 3rd part where
	1. we pattern match `f`
	2. Then we check if both the lists are non empty
	3. Then return the output

This example demonstrates an obvious inefficiency in this approach.
Whenever we get an input that gets evaluated on multiple guards before reaching the correct one, we recompute the same matches multiple times, for examples if our input is 
```
(+) [1,2] [3,4]
```
then we match all the inputs thrice, there should be a way to match each input at most once, like one would be able do in their head.

---
## Case Statement
To deal with the redundant computations, we rewrite the lambda expression using match case, then we get
```haskell
zipWith = 
  \f->(\xs'->(\ys'->
    case xs' of
      Nil    => Nil
      (x:xs) => case ys' of
                  Nil    => Nil
                  (y:ys) => (f x y) : zipWith xs ys))
```

One way to convert pattern match expressions to case statements is the [[Match Function for Enriched Lambda Calculus|Match Function]]

---
# References
- [[Patterns]]
- [[Enriched Lambda Calculus]]
- [[Translating Haskell Programs to Lambda Calculus]]
- [[Match Function for Enriched Lambda Calculus]]