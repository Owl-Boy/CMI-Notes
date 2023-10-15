---
tags:
  - Note
---
202309281809

Tags : [[Advanced Algorithms]]

---
# Approximation Algorithms

```ad-tip
title: Motivation

In life we are faced with a lot of problems. Some of them are *Decision Problems*: (Yes/No)
- Is there a path of weight $\le w$ from $s$ to $t$ in $G$?

Some are *Optimization Problems*: (Each solution has a cost.)
- Find the min cost/weight path from $s$ to $t$ in $G$.
- Find the min cost brain we can replace my friend's with.
In this course, we will mostly concern ourselves with the latter.

Because we believe that we can't find optimal solutions to all of these fast $(P\neq NP)$, we try coming up with *Approximation Algorithms*, which we then prove to not be <i>that</i> far from optimal.

```

```ad-note
*$NP$ complete problems* are decision problems in $NP$ s.t. every problem in $NP$ reduces to them in polytime.
Polytime algo for one $NP$ complete problem $\implies$ polytime algo for all $NP$ problems.
```
## Approximation
**Definition:** An algorithm $A$ is said to be an $\alpha$-approximation for an optimisation problem if for every instance $I$,
$$
\begin{align*}
\frac{A(I)}{OPT(I)}&\le \alpha &&\text{Minimisation}\\\\
\frac{OPT(I)}{A(I)}&\le \alpha &&\text{Maximisation}
\end{align*}
$$

```ad-note
Approximation is good as a ratio and not as an additive factor because we can scale and ignore the additive factor.
```

---
# References
[[Vertex Cover Problem]]