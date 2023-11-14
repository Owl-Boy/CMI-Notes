---
tags:
  - Note
---
202310251510

Tags : [[Programming Languages]]

---
# Empty Rule for Match Function
After applying the other rules(possibly multiple times),  we will reach the following situation

## Example
```haskell
match []
      [ ( [], (A u1 u3) ) ]
      ERROR
```

which intuitively reduces to 
```haskell
A u1 u2
```

---
## Empty Rule
In the general case, the list of expressions might be empty for might have multiple arguments.
Hence given the expression
```haskell
match []
      [ ([], E1),
        ...
        ([], Em)]
      E
```
where $m\ge 0$. and we define match to give the following in this situation
```
E1 |> ... |> Em |> E
```

---
# References
- [[Match Function for Enriched Lambda Calculus]]
- [[Constructor Rule for Match Function]]
- [[Variable Rule for Match Function]]
- [[Mixture Rule for Match Expression]]