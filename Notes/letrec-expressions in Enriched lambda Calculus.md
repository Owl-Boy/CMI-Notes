---
tags:
  - Note
---
202310201710

Tags : [[Lambda Calculus]], [[Programming Languages]]

---
# letrec-expressions in Enriched lambda Calculus
The syntax of $\text{letrec-}$expressions is similar to $\text{let-}$expressions.
```
letrec v1 = E1
       v2 = E2
       ...
       vn = En
in
       E
```
where `v1`..`vn` are variables and `E`, `E1`..`En` are expressions in **Enriched Lambda Calculus**

the term `letrec` is short for *let recursively*, it introduces the possibility to define variables recursive, the difference between `let` and `letrec` is that the scope of any `v` is `E` and all of the `E1`..`En`.

**Example:**
```
letrec fac = \n IF (= n 0) 
                   1 
                   (* n (fac (- n 1)))
in     fac 4
```
---

Multi-line definitions are necessary for `letrec` for example
```
letrec f = ... f ... g
       g = ... f ...
in ...
```
Here nesting makes the inner definition out of scope for the outer one.

---

The semantics for single definition `letrec` is given by the Y combinator.
we say
```
letrec v = B in E <=> let v = Y (\v.B) in E
```

---
# References
[[Enriched Lambda Calculus]]
[[let-expressions in Enriched Lambda Calculus]]