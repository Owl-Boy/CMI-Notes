---
tags:
  - Note
---
202310251710

Tags : [[Programming Languages]]

---
# Mixture Rule for Match Expression

The *Mixture Rule* deals with the case where a set of patterns contain both variables and constructors, hence neither of the [[Match Function for Enriched Lambda Calculus#Simplification Rules|other rules]] apply.

We combine the [[Variable Rule for Match Function|Variable Rule]] and [[Constructor Rule for Match Function|Constructor Rule]] in this situation.

## Example
Consider the variant of the `demo` function that was defined in the [[Match Function for Enriched Lambda Calculus|Main Page]]
```haskell
demo' f []     ys     = A f ys
demo' f xs     []     = B f xs
demo' f (x:xs) (y:ys) = C f x xs y ys
```

In this case we reach the following situation after applying the [[Variable Rule for Match Function|Variable Rule]] once.

```haskell
match [u2, u3]
      [ ([NIL   , ys]    , A u1 ys),
        ([xs    , NIL]   , B u1 xs),
        ([(x:xs), (y:ys)], C u1 x xs y ys)]
       Error
```

due to the semantics of *match*, if all patterns fail, the function returns its third input, we can use that by only considering the patterns until it changes from variable to constant or vice versa. Check just until then, and move to the other patterns if the first set fails. We write that in the following way

```haskell
match [u2, u3]
      [([NIL, ys], A u1 xs)]
      (
        match [u2, u3]
              [ ([xs, NIL], B u1 xs),
                ([(x:xs), (y:ys) C u1 x xs y ys])]
              Error
      )    
```

---
## Mixture Rule
Using the above example, we can say the following
```haskell
match us qs E
```

where `qs = qs1 ++ ... ++ qsk`, and each `qsi` is a partition that contains only *Constructors* or only *Variables* for the first argument.

we can rewrite it as
```haskell
match us qs1 (match us qs2(...(match us qsk E)...))
```

---
# References
- [[Match Function for Enriched Lambda Calculus]]
- [[Variable Rule for Match Function]]
- [[Constructor Rule for Match Function]]
- [[Empty Rule for Match Function]]
