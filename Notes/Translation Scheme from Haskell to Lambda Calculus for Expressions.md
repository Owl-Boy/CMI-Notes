---
tags:
  - Note
  - Incomplete
---
202310210310

Tags : [[Programming Languages]]

---
# Translation Scheme from Haskell to Lambda Calculus for Expressions

We describe $\mathbf{TE}$ by case analysis of forms of *Haskell* expressions.

## Constants
The constants or built-in functions are all the same set of constants for [[Enriched Lambda Calculus]], so the following rule is enough
$$
\mathbf{TE}\textlbrackdbl\; k\; \textrbrackdbl = k'
$$
where $k'$ refers to the constant defined in *Lambda Calculus* which corresponds to $k$ defined in *Haskell*.

---
## Variables
Similar to the above translation, this is enough
$$
\mathbf{TE}\textlbrackdbl\; v\;\textrbrackdbl= v
$$
where $v$ is a variable (including names of user defined functions and constructors)

---
## Function Application
Function application in *Haskell* is denoted by juxtaposition, which is the same as the syntax used in *Lambda Calculus*
$$
\mathbf{TE}\textlbrackdbl\;E_{1}\;E_{2}\;\textrbrackdbl = \mathbf{TE}\textlbrackdbl\;E_{1}\;\textrbrackdbl \quad \mathbf{TE}\textlbrackdbl\;E_{2}\;\textrbrackdbl  
$$
But *Haskell* also provides an option to use **Infix**(operator between the operands) notation. This translates to 
$$
\mathbf{TE}\textlbrackdbl\;E_{1}\;\text{infix}\;E_{2}\;\textrbrackdbl = 
\mathbf{TE}\textlbrackdbl\;\text{infix} \;\textrbrackdbl \quad  
\mathbf{TE}\textlbrackdbl\;E_{1}\;\textrbrackdbl \quad 
\mathbf{TE}\textlbrackdbl\;E_{2}\;\textrbrackdbl  
$$
And it allows the user defined operators to infix by putting them in \` (back-tick)

$$
\mathbf{TE}\textlbrackdbl\;E_{1}\;\text{`v`}\;E_{2}\;\textrbrackdbl = 
\mathbf{TE}\textlbrackdbl\;\text{`v`} \;\textrbrackdbl \quad  
\mathbf{TE}\textlbrackdbl\;E_{1}\;\textrbrackdbl \quad 
$$

---
## Summary
![[Pasted image 20231022202545.png]] ^76f158

---
# References
[[Translation Scheme from Haskell to Lambda Calculus for Expressions]]
[[Translation Scheme from Haskell to Lambda Calculus for Definitions]]
[[Translating Haskell Programs to Lambda Calculus]]