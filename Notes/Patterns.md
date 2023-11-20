---
tags:
  - Note
---
202310221810

Tags : [[Programming Languages]]

---
# Patterns
```ad-info
title:Definition
A pattern $p$ is either
- a variable $v$
- a constant $k$
- a constructor pattern of the form $(c\;p_1\;p_{2\dots}p_n)$ where $p_{i}$ are also patterns

In case of *Haskell* all variables should be distinct
```
---
Consider the following Haskell function
```haskell
f p1 = E2
f p2 = E2
...
f p3 = E3
```
```ad-summary
title:Intuition
The intuitive semantics of pattern matching are  "Try the first pattern, if that fails then try the next, and so on". This suggests that all of them might fail, in which case an error.

We introduce values $\text{FAIL}$ and $\text{ERROR}$
```
The following is the definition of `f` into [[Enriched Lambda Calculus]].

```
f = \x.(  ((\p1'.E1') x)
       |> ((\p2'.E2') x)
       ...
       |> ((\pn'.En') x)
       |> ERROR )
```
here `x` is a new variable which is not free in any `E`.

---
## Semantics for the $\triangleright$ operator

```ad-warning
title: Notation Difference
The book uses a symbol called fatbar instead of $\triangleright$, I cannot find the latex definition for it.
```

The function `|>` is an infix function whose behavior is described by
$$
\begin{align*}
a &\triangleright b = a\\
\text{FAIL} &\triangleright b = b\\
\perp &\triangleright b = \perp
\end{align*}
$$
Operationally, `|>` evaluates the left argument, and if the evaluation terminates and yields anything other than $\text {FAIL}$ then it returns that, otherwise it returns the second argument.
`|>` is associative and has identity $\text{FAIL}$.

Suppose `f` is applied to multiple arguments, and one of the initial arguments fails. Then we want the failure to propagate, hence we need the following reduction rule for $\text{FAIL}$

$$
\text {FAIL}\;\;E\quad \to\quad\text{FAIL}
$$
This property is followed by the fixed point of the $K$ combinator called **Eater**. 

---
## Semantics of Pattern Matching
### Variables
The the pattern is a variable $v$, then the pattern matching lambda abstraction is just an ordinary lambda abstraction.

### Constants
Semantics for constant patterns state that if the argument matches the constant value then we use that value in the expression, otherwise we return fail, this can be written as 

$$
\begin{align*}
&\mathbf{Eval}\textlbrackdbl\;\lambda k.E\;\textrbrackdbl\;a = 
\mathbf{Eval}\textlbrackdbl\;E\;\textrbrackdbl &&\text{if }a=\textbf{Eval}\textlbrackdbl\;k\;\textrbrackdbl\\
&\mathbf{Eval}\textlbrackdbl\;\lambda k.E\;\textrbrackdbl\;a =\text{FAIL}
&&\text{if }a\ne\textbf{Eval}\textlbrackdbl\;k\;\textrbrackdbl\text{ and } a\ne\perp\\
&\mathbf{Eval}\textlbrackdbl\;\lambda k.E\;\textrbrackdbl\perp =\; \perp
\end{align*}
$$

^974443

### Sum Constructors
The idea is somewhat similar, we first check if the constructor matches for the pattern, then we recursively pattern match each field of the constructor. We fail if the constructor does not match.
$$
\begin{align*}
&\mathbf{Eval}\textlbrackdbl\;\lambda (s\;p_{1}\dots p_{k}).E\;\textrbrackdbl\;(s\;a_{1}\dots a_{k}) &&=  
\mathbf{Eval}\textlbrackdbl\;\lambda p_{1}\dots \lambda p_{k}.E\;\textrbrackdbl \; a_{1}\dots a_{r}\\
&\mathbf{Eval}\textlbrackdbl\;\lambda (s\;p_{1}\dots p_{k}).E\;\textrbrackdbl\;(s'\ a_{1}\dots a_{k}) &&=  \text{FAIL}\quad\quad\text{ if } s\ne s'\\
&\mathbf{Eval}\textlbrackdbl\;\lambda (s\ p_{1}\dots p_{k}).E\;\textrbrackdbl\perp &&= \; \perp
\end{align*}
$$

^b7ccdc

### Product Constructor
The reason why this is a different section is because we choose to make the product constructors lazy, specifically to handle the case when none of the components are used.

$$
\begin{align*}
\mathbf{Eval}\textlbrackdbl\;\lambda(t\ p_{1}\dots p_{r}).E\;\textrbrackdbl\; a =  \mathbf{Eval}\textlbrackdbl\;\lambda p_{1}\dots \lambda p_{r}.E\;\textrbrackdbl\;&(\text{SEL-t-}1\;a)\\
&\dots\\
&(\text{SEL-t-}r\;a)
\end{align*}
$$

^55a864

Where $\text{SET-t-}i$ is a built in function that extracts the $i^{th}$ component of $a$.
$$
\begin{align*}
&\text{SET-t-}i\ (t\ a_{1}\dots a_{i}\dots a_{r})&&= a_i\\
&\text{SET-t-}i\ \perp &&= \perp
\end{align*}
$$
This ensure that if none of the components of a product are evaluated, the product is not evaluated either.

---
# References
[[Evaluating Pattern Matching in Lambda Calculus]]