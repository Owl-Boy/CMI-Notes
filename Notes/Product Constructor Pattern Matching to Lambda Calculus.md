---
tags:
  - Note
  - Incomplete
---
202311041811

Tags : [[Programming Languages]]
# Product Constructor Pattern Matching to Lambda Calculus
---
This pattern checks if the given input is some product constructor of arity $r$ and is written as

$$
(\lambda t\ p_{1}\ p_{2}\dots p_{r})
$$

The semantics of the **Product Constructor** pattern is
![[Patterns#^55a864]]

To implement this, we create a built in function $\text{UNPACK-PRODUCT-t}$ and use it in the transformation

$$
(\lambda(t\ p_{1} p_{2} \dots p_{r}).E)\quad\equiv\quad 
\text{UNPACK-PRODUCT-t}\; (\lambda p_{1}\ p_{2}\dots p_{r}.E)
$$
And the inbuilt function is defined in the following way

$$
\text{UNPACK-PRODUCT-t}\; f\; a\quad\equiv\quad f\; (\text{SEL-t-1}\; a)\dots(\text{SEL-t-r}\; a)
$$

>[!example]
>Consider the following Haskell program
>```haskell
>add_pair (x, y) = x + y
>```
>which gets converted to 
>```haskell
>add_pair = \(PAIR x y). + x y
>```
>which will be converted to 
>```haskell
>add_pair = UNPACK-PRODUCT-PAIR (\x y. + x y)
>```
 
---
# References
[[Patterns]]