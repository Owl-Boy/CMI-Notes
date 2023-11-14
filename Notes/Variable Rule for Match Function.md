---
tags:
  - Note
---
202310251510

Tags : [[Programming Languages]]

---
# Variable Rule for Match Function

## Example
In the example given in the [[Match Function for Enriched Lambda Calculus|Main note]]
```haskell
demo =
  \u1. \u2. \u3. 
    match [u1, u2, u3]
          [ ( [f, [],     ys],     (A f ys)  ),
            ( [f, (x:xs), []],     (B f x xs)),
            ( [f, (x:xs), (y:ys)], (C f x xs y ys)) ]
          ERROR
```
This can be reduced to the equivalent form
```haskell
demo =
  \u1. \u2. \u3. 
    match [u2, u3]
          [ ( [[],     ys],     (A u1 ys)  ),
            ( [(x:xs), []],     (B u1 x xs)),
            ( [(x:xs), (y:ys)], (C u1 x xs y ys)) ]
          ERROR
```

---

## Variable Rule
The variable rule is the conversion defined as follows

```haskell
match (u:us)
      [ ( (v1:ps1), E1 ),
        ...
        ( (vm:psm), Em )]
      E
```
will get transformed to
```haskell
match us
      [ ( ps1, E1[u/v1] ),
        ...
        ( psm, Em[u/vm] )]
      E
```

This rule formalizes the statement that if the pattern to be match is a variable, then it is always accepted without any conditions.

---
# References
- [[Match Function for Enriched Lambda Calculus]]
- [[Constructor Rule for Match Function]]
- [[Empty Rule for Match Function]]
- [[Mixture Rule for Match Expression]]