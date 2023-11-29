---
tags:
  - Note
  - Incomplete
---
202311291711

Tags : [[Logic]]
# N_L admits Quantifier Elimination
---
As discussed in [[Quanitifier Elimination for Natural Numbers With Successor]]. It is sufficient to consider formulas of the form 
$$
\exists x(\alpha_{1}\land\alpha_{2}\dots \alpha_{n})
$$
such that each $\alpha_i$ contains $x$. And there is no negation.

If an atomic formula is a congruence, Then we replace all the instances of the variable with the other side of the congruence.

Otherwise all of the formulae are inequalities. Say it is of the form
$$
\exists x \Big(\bigwedge_{i} t_{i}<\mathbf{S}^{m_{i}}(x)\quad\land\quad \bigwedge_{j}S^{n_{j}}(x)<u_{j} \Big)
$$

>[!note] Idea
>We have a block of lower bounds followed by a block of upper bounds.
>We need to have a gap between the biggest lower bound and the smallest upper bound, but since we do not have a max and min function, we can check if there is a gap between every lower bound and upper bound. And that every upper bound is positive.

We successively rewrite it as
$$
\begin{align}
\exists x \bigwedge_{i,j} (t_{i}<\mathbf{S}^{m_{i}}x\quad\land\quad \mathbf{S}^{n_{j}}<u_{j})\\
\exists x \bigwedge_{i,j} (\mathbf{S}^{n_{j}}t_{i}<\mathbf{S}^{m_{i}+n_{j}}x<\mathbf{S}^{m_{i}}u_{j}) \\
\exists x \bigwedge_{i,j} (\mathbf{S}^{n_{j}+1}t_{i}<\mathbf{S}^{m_{i}}u_{j})\quad\land\quad \bigwedge_{j}\mathbf{S}^{n_{j}}\mathbf{0}<u_{j} \\
\end{align}
$$




---
# References
[[Quanitifier Elimination for Natural Numbers With Successor]]