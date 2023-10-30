---
tags:
  - Example
---

202310291633

tags : [[Programming Languages]]

#  False Assumptions easy to make about Patterns
---

## Symmetry
Consider the following function

```haskell
zipWith' f []     ys     = []
zipWith' f xs     []     = []
zipWith' f (x:xs) (y:ys) = f x y : zipWith' f xs ys
```

and consider the following evaluation

```haskell
zipWith' (+) bottom []
```

where evaluations of the `bottom` would fail to terminate because it is matched against `[]` for the first pattern. 

On the other hand
```haskell
zipWith' (+) [] bottom
```
does terminate because the first pattern matches.

Hence even though the function definition does look like it should be symmetric in the sense that if one of the inputs is empty then other one does not matter. 

This is not true for the original definition
```haskell
zipWith f []     ys     = []
zipWith f (x:xs) []     = []
zipWith f (x:xs) (y:ys) = f x y : zipWith xs ys
```
This definitions makes the asymmetry apparent.

---
## Ordering Non-overlapping Patterns
Consider the following function definition

```haskell
diagonal x     True  False = 1
diagonal False y     True  = 2
diagonal True  False z     = 3
```

These 3 equations are all non-overlapping, however another false assumption that is easy to make because of this is that, it should just be fair to reorder these without changing the function. However there is a slight problem with this, the slight problem being the evaluation of 
```haskell
diagonal bottom True False
```
Under the above definition, this evaluates to $1$, but if any other expressions was return before the first one, this would not have evaluated.

>[!success] [[Uniform Definition of Haskell Functions]]
>The set of definitions that that do have the property that they can be reordered  are called **Uniform Definitions**
 
---
# Related
- [[Ordering Equations in Uniform Definitions]]
- [[Independence of meaning from changing the order on the left hand side implies uniform definition]]
- [[Uniform Definition of Haskell Functions]]