---
tags:
  - Note
---
202310290210

Tags : [[Programming Languages]]
# Optimisations for Overlapping Patterns
---

>[!warning] Overlapping Patterns
> If overlapping equations are allowed, then sometimes the pattern-matching compiler may transform a small set of equations in to a _case-expression_ which is much larger.

## Redundancies created due to Constructor Rule

This is a problem that is created by the [[Constructor Rule for Match Function]] where expressions of the form

```
match (u:us) (qs1 ++ ... ++ qsk) E
```
to
```haskell
case u of
    c1 us1' => match (us1' ++ us) qs1' E
    ...
    ck usk' => match (usk' ++ us) qsk' E
```

Normally `E` would be $\text{ERROR}$, but if [[Mixture Rule for Match Expression|Mixture Rule]] is used then `E` can be huge. So we modify the rule in the following way to avoid duplication

```haskell
(case u of
    c1 us1' => match (us1' ++ us) qs1' FAIL
    ...
    ck usk' => match (usk' ++ us) qsk' FAIL)
|> E
```

^11a949

---

## Example Problem
```haskell
unwieldy [] [] = A
unwieldy xs ys = B xs ys
```

Here the [[Match Function for Enriched Lambda Calculus|pattern matching compiler]] transforms the above set of equations to

```haskell
unwieldy =
    \xs.\ys. case xs of
                Nil         => case ys of
                                   Nil         => A
                                   Case y' ys' => B xs ys
                Cons x' xs' => B xs ys
```

where `B xs ys` is repeated. This would get worse as the number of repetitions or the size of `B` increases and make the compiled binaries huge.

Using the rules above we get
```haskell
unwieldy =
    \xs.\ys. (case xs of
                Nil         => (case ys of
                                   Nil         => A
                                   Case y' ys' => FAIL)
                               |> Fail
                Cons x' xs' => FAIL)
             |> B xs ys
```
this may be bigger, but it has just one occurrence of `B` hence, if the size of `B` explodes, the the upper one grows much faster.

---
# References
- [[Match Function for Enriched Lambda Calculus]]
- [[Patterns]]
- [[Evaluating Pattern Matching in Lambda Calculus]]
