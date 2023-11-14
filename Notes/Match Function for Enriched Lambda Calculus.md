---
tags:
  - Note
---
202310251410

Tags : [[Programming Languages]]

---
# Match Function for Enriched Lambda Calculus

Our goal is to convert an equation of the form
$$
\begin{align*}
&((\lambda p_{1,1}\dots\lambda p_{1,n}.E_{1})\; u_{1}\dots u_{n})\\
\triangleright\quad &\vdots\\
\triangleright\quad &((\lambda p_{m,1}\dots p_{m,n}.E_{m})\; u_{1}\dots u_{n})\\
\triangleright\quad&E
\end{align*}
$$
We first convert the above from into the following and then use the **match** function to simply it in multiple steps, starting from the leftmost pattern to the rightmost one
$$
\begin{align*}
\textbf{match}\quad
&[u_{1},\ \dots,\ u_n]\\
&[(\; [p_{1,1},\ \dots,\ p_{1,n}],\ E_1\;),\\
&\vdots\\
&(\; [p_{m,1},\ \dots,\ p_{m,n}],\ E_{m}\;)]\\
&E
\end{align*}
$$

## Example of conversion from Lambda Calculus to Match function

```haskell
demo f []      ys     = A f ys
demo f (x: xs) []     = B f x xs
demo f (x: xs) (y:ys) = C f x xs y ys
```

This can be converted to the following program in [[Enriched Lambda Calculus]]

$$
\begin{align*}
= \lambda u_{1}.\lambda u_{2}.\lambda u_{3}&.
&&((\lambda f.\lambda [].\lambda ys.\ A\ f\ ys)\; u_{1}\ u_{2}\ u_{3})\\
&\triangleright
&&((\lambda f.\lambda (x:xs).\lambda [].\ B\ f\ x\ xs)\; u_{1}\ u_{2}\ u_{3})\\
&\triangleright
&&((\lambda f.\lambda (x:xs).\lambda (y:ys).\ C\ f\ x\ xs\ y\ ys)\; u_{1}\ u_{2}\ u_{3})\\
&\triangleright
&&\text{ERROR}
\end{align*}
$$

This can be converted to use the *match* function in the following way

```haskell
demo =
  \u1. \u2. \u3. 
    match [u1, u2, u3]
          [ ( [f, [],     ys],     (A f ys)  ),
            ( [f, (x:xs), []],     (B f x xs)),
            ( [f, (x:xs), (y:ys)], (C f x xs y ys)) ]
          ERROR
```

^92bf09

---
## Simplification Rules
The following rules are used repeatedly to convert *match* syntax to $\text{case-}$expressions ^b05ec8
- [[Variable Rule for Match Function|Variable Rule]] when all patterns are variables
- [[Constructor Rule for Match Function|Constructor Rule]] when all patterns are constructor
- [[Mixture Rule for Match Expression|Mixed Rule]] when some of the patters are variables and some are constructors
- [[Empty Rule for Match Function|Empty Rule]] to remove the match function to get only case expressions.

---
# References
- [[Optimisations for Overlapping Patterns]]
- [[Optimisations for Expressions containing FAIL and I>]]
- [[Uniform Definition of Haskell Functions]]