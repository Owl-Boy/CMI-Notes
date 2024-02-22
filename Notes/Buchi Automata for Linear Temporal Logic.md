---
tags:
  - Note
  - Incomplete
---
202402211202

Tags : [[Logic]], [[Automata Theory]]
# Buchi Automata for Linear Temporal Logic
---
Given a Linear Temporal Logic formula $\varphi$, let $\sigma$ be a sequence of valuations that satisfy $\varphi$ at $0^{\text{th}}$ index.
Let a the Alphabet be the set of all possible valuations of free variables are used in $\varphi$.
Then we can construct a [[Büchi Automata]] accepts exactly the words that corresponds to sequence of structures that satisfy $\varphi$.

>[!definition] Closure of a Formula
>It will be hard to model all the LTL formule, so we introduce more letters to the alphabet, to carry more information. Given a formula $\varphi$ we define the closure of the formula as
>$$
>\begin{align}
>\mathbf{Cl}(\varphi)&= \text{The set of all subformulae of $\varphi$
} \cap\\ &\text{If the forumula contains the $\mathcal U$}\\ &\text{then we add $X$ of the formula to the closure too} 
>\end{align}
>$$

>[!todo] atoms of the closure



---
# References
