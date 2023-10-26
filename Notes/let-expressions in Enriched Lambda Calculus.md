---
tags:
  - Note
---
202310201710

Tags : [[Lambda Calculus]], [[Programming Languages]]

---
# let-expressions in Enriched Lambda Calculus
$\text{let-}$expressions are a way to bound a name to value within a given expression, written as 
```
let v = B in E
```
which means, that the variable `v` is bound to the expressions `B`. The scope of this definition is the expression `E`. 

**Example 1:** `+ 1 (let x = 3 in (* x x))`
The evaluations of the above expression is as follows

```
   + 1 (let x = 3 in (* x x))
-> + 1 (* 3 3)
-> + 1 9
-> 10
```
---
let expressions can also be embedded within other expression, including other let expressions, like

**Example 2:** `let x = 3 in (let y = 4 in (* x y))`
The evaluation of the above expression would  be
```
   let x = 3 in (let y = 4 in (* x y))
-> let x = 3 in (* x 4)
-> * 3 4
-> 12
```

as a matter of convenience, the above expression is written as
```
let x = 3
    y = 4
in  (* x y)
```
---
the semantics can be given as
```
let v = B in E <=> (\v. E) B
```

---
# References
[[Enriched Lambda Calculus]]
[[letrec-expressions in Enriched lambda Calculus]]