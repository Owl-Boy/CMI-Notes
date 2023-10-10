---
tags:
  - Note
---
202309210909

Tags : [[Logic]], [[Lambda Calculus]]

---
# Lambda Term In Combinatory Logic
For any $F$ and $x$, we can define 
$\lambda^{*}xF\in\mathcal C$
$$
\begin{align*}
\lambda^{*}x.x &= \underline I\\
\lambda^{*}x.F &= \underline K F &\text{where }x\notin\text{vars}(F)\\
\lambda^{*}x.FG &= \underline S(\lambda^{*}x.F)(\lambda^{*}x.G)
\end{align*}
$$

As an example, we have the $Y$ Combinator $\lambda f.(\lambda x.f(xx))(\lambda x.f(xx))$

We can add Types to our combinatory logic analogous to Lambda Calculus and get [[Typed Combinatory Logic]]

This shows that *Combinatory Logic* is just as strong as *Lambda Calculus* and that the $S,K$ Combinators are Complete.

---
# References
[[Combinatory Logic]]
[[Lambda Calculus Syntax|Lambda Calculus]]