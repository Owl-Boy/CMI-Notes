---
tags:
  - Note
  - Incomplete
---
202311071911

Tags : [[Programming Languages]]
# Conformality Transformation on let(rec) expression
---
Consider the example
```haskell
head xs = y
  where (y:ys) = xs
```

There is an obvious way in which the above function fails, i.e if the function is given an empty list as in input.

This can happen in case of [[Patterns#Sum Constructors|sum patterns]] and [[Patterns#Constants|constant patterns]] and converting it to [[Enriched Lambda Calculus]] does not fix the problem

```ocaml
head = \xs.(let (CONS y ys) = xs in y)
```

we convert `CONS` to `PAIR` in the following way

```haskell
head := 
    \xs.((let (PAIR y ys) 
        = (\(CONS y ys).PAIR y ys) xs) |> ERROR in y)
```
in general for 
```haskell 
p = B
```
we get

```haskell
(t v1 ... vn) = ((\p.(t v1 ... vn)) B) |> ERROR
```

Here `t` is a Product constructor so the pattern is [[Irrefutable let(rec)|irrefutable]].

---
# References
