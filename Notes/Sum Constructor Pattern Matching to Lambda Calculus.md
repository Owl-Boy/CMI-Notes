---
tags:
  - Note
  - Incomplete
---
202311041911

Tags : [[Programming Languages]]
# Sum Constructor Pattern Matching to Lambda Calculus
---
This pattern checks if the given input matches one of the sum constructors of arity $r$ which is written as
$$
\lambda(s\ p_{1}\dots p_{r})
$$
and the semantics is given by
![[Patterns#^b7ccdc]]

Once again, we make a new function $\text{UNPACK-SUM-s}$ and use it to implement the above in the following way
$$
(\lambda(s\ p_{1} p_{2} \dots p_{r}).E)\quad\equiv\quad 
\text{UNPACK-SUM-t}\; (\lambda p_{1}\ p_{2}\dots p_{r}.E)
$$
and we define $\text{UNPACK-SUM-s}$ in the following way
$$
\begin{align}
&\text{UNPACK-SUM-s}\ f\ (s\ a_{1}\dots a_{r})\quad&&\equiv\quad f\ a_{1}\dots a_{r}\\
&\text{UNPACK-SUM-s}\ f\ (s'\ a_{1}\dots a_{r})\quad&&\equiv\quad \text{FAIL} &\text{if }s'\ne s \\
&\text{UNPACK-SUM-s}\ f\ \bot\quad&&\equiv\quad\bot
\end{align}
$$

>[!example]
>Consider the following Haskell Program
>```haskell
>reflect (LEAF n) = LEAF n
>reflect (BRANCH t1 t2) = BRANCH (reflect t2) (reflect t1)
>```
>which gets converted to 
>```haskell
>reflect = \t.( ((\(LEAF n).LEAF n) t)
>             |> ((\BRANCH t1 t2).BRANCH (reflect t2) (reflect t1) t)
>             |> ERROR)
>```
>and this translates to
>```haskell
>>reflect = \t.( UNPACK-SUM-LEAF (\n.LEAF n) t)
>             |> (UNPACK-SUM-BRANCH (\t1 t2.BRANCH (reflect t2) (reflect t1)) t)
>             |> ERROR)
>```
---
# References
[[Patterns]]