---
tags:
  - Note
  - Incomplete
---
202311041811

Tags : [[Programming Languages]]
# Constant Pattern to Lambda Calculus
---

This pattern checks if a given argument matches a particular constant or a lambda expression. written as 
$$
(\lambda k.E)
$$
The semantics of the **Constant** pattern give
![[Patterns#^974443]]

Hence we can simply replace these expressions with
$$
(\lambda k.E) \quad\equiv\quad (\lambda x.\text{IF}\;(=\; k\; v)\;\; E\;\; \text{FAIL})
$$

>[!example]
> Consider the following Haskell Program
> ```haskell
> flip 0 = 1
> flip 1 = 0
> ```
> which gets converted to
> ```haskell
> flip = \x.( ((\0.1) x)
>          |> ((\1.0) x)
>          |> ERROR )
>  ```
>  Applying the above rule converts it to the following lambda expression
>  ```haskell
> flip = \x.( ((\v. IF (= v 0) 1 FAIL) x)
>           |> ((\v. IF (= v 1) 0 FAIL) x)
>           |> ERROR )
>  ```


---
# References
[[Patterns]]