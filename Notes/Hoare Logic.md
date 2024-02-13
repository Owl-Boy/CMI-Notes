---
tags:
  - Note
  - Incomplete
---
202402121602

Tags : [[Logic]] [[coq]] 
# Hoare Logic
---
A hoare triple is a triple of property $\alpha$, a sequence of steps $c$ and another property $\beta$. such that 
$$
\forall s,s'. s \models \alpha \land s-\!\!\![c]\!\!\!\to s' \implies s' \models \beta 
$$
$$
\begin{align}
\alpha ,\quad&\text{SKIP},\quad\alpha \\
\{\alpha \; [X\mapsto e]\},\quad &X:= e,\quad\{ \alpha\} \\

\end{align}
$$

---
# References
