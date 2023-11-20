---
tags:
  - Note
  - Incomplete
---
202311072011

Tags : [[Programming Languages]]
# letrec-expressions to Irrefurtable let-expressions
---
A *letrec* with a single definition, can be converted as follows
```haskell
letrec v = B in E   ===   let v = Y(\v.B) in E
```

To extend this definition for the general case, we first convert a *letrec* so that it will have just 1 definition as follows

```haskell
letrec p1 = B1   ===   letrec (t p1 ... pn) = (t B1 ... Bn) in E
       ...
       pn = Bn
in E
```

Now we use the above idea to get 
```haskell
letrec p = B in E    ===    let p = Y(\p.B) in E
```


---
# References
