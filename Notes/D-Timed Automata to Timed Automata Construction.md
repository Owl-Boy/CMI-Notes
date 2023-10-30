---
tags:
  - Example
---

202310282042

tags : [[Timed Automata]]

#  D-Timed Automata to Timed Automata Construction
---
>[!hint] Idea
>We use extra states to represent if the diagonal constraints are true or false, in each transition we check if the value of the diagonal constraints change or not.
>

Consider  a *d-timed automaton* with just $1$ diagonal constraint.
Let $\mathcal A=(Q,\Sigma,X,T,q_{0},F)$ be that *d-timed automaton* 
We construct $\mathcal A'$ where $Q' = Q \times \{\bot,\top\}$ where $(q,\top)$ represents the automata is in state $q$ and the clock $x,y$ are in a configuration where they do satisfy the diagonal guard.
we also have 
- $\Sigma'=\Sigma$
- $X'=X$
- $q_{0}'=(q_{0},\top)$ if $c\ge 0$ otherwise its $(q_0,\bot)$
- $F'=F\times\{\top,\bot\}$ 

For the transitions we have the following cases
- If $x,y\not\in R$ then we have the following transitions instead of the transition with diagonal guard
$$
(q, 0)\xrightarrow[R]{\quad g\quad}(q',0)\quad\quad\text{and}\quad\quad(q, 1)\xrightarrow[R]{\quad g\quad}(q',1)
$$
  because the value of $x-y$ does not change until the clocks are reset, so the guards will remain satisfied or unsatisfied and not switch.
- If $x, y \in R$ then we have 
$$
\begin{align*}
(q,b)\xrightarrow[R]{\quad q\quad}(q',1) \text{ if } 0\le c\\
(q,b)\xrightarrow[R]{\quad q\quad}(q',0) \text{ if } 0> c\\
\end{align*}
$$
- If $x\in R$ and $y\notin R$
$$
(q, b)\xrightarrow[R]{\quad g\; \land\; -y \leq c\quad}(q',1)\quad\quad\text{and}\quad\quad(q, b)\xrightarrow[R]{\quad g\;\land\; -y>c\quad}(q',0)
$$
- If $x\notin R$ and $y\in R$
$$
(q, b)\xrightarrow[R]{\quad g\; \land\; x \leq c\quad}(q',1)\quad\quad\text{and}\quad\quad(q, b)\xrightarrow[R]{\quad g\;\land\; x>c\quad}(q',0)
$$
 Not he construction of $\mathcal A'$ is complete, we successfully removed one diagonal transition.

>[!summary] Generalization
>For any arbitrary [[Timed Automata with Diagonal Constraints|d-timed automaton]] we can repeat this procedure of every clock. Hence every *d-timed automata* can be converted to a *timed automata*.


---
# Related
- [[Timed Automata with Diagonal Constraints]]