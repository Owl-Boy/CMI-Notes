---
tags:
  - Note
  - Incomplete
---
202311180011

Tags : [[Timed Automata]]
# Dimension of a Path
---
>[!tip] Motivation
> We here want to embed each [[Timed Automata Alternate Definition#Semantics of Timed Automata|Path]] in some $\mathbb R^n$. In doing so, the idea of the *Dimension* of a Path naturally arises. Its the smallest $n$ such that the path in some sense can be embedded in $R^n$.

The idea is to consider $\tau_i$ corresponding to each edge in the path, and use it add a dimension to the path.
- If set of possible $\tau_i$ is a singleton in all cases. or if its empty. Then the edge does not add dimension to the path.
- Otherwise we add a dimension

>[!example] 
>![[Pasted image 20231118002432.png]]
>let $s_0 = (l_0,0)$ and $\pi$ be the path $\pi(s_0, e_1, e_2)$
>Then it is easy to associate the following polygon to the path
>$\text{Pol}(\pi)=\{ (\tau_{1},\tau_{2})\in \mathbb R^2 \;:\;(0\leq \tau_{1}\leq2)\land(0\leq \tau_{1}+\tau_{2}\leq 5)\}$ so $\pi$ has dimension 2
>but the path $\pi'=\pi(s_{0},e_{1},e_{3})$ has dimension 1 but is embedded in 2 dimension.
>So we say that the dimension of $\pi'$ is undefined.

For a constrained path is the polygon corresponding to path intersected with the polygon corresponding to the constraint.(sort of)

$$
\text{Pol}(\pi_{\mathbb C})=\{ (\tau_{i})_{1\leq i\leq n} \in \mathbb R_{+}\;:\;s\xrightarrow{\tau_{1},e_{1}}s_{1}\cdots\xrightarrow{\tau_{n},e_{n}}s_{n}\in \pi_{\mathcal C}(s,e_{1}\dots e_{n}) \}
$$

>[!note] Definition
>Let $\mathcal A$ be a *Timed Automaton* and $\pi_{\mathcal C}=\pi_{\mathcal C}(s,e_{1}\dots e_{n})$ be a constrained path. For each $i\leq n$ we write $\mathcal C_i$ to be the projection of $\text{Pol}(\pi_{\mathcal C})$ over the variables of first $i$ coordinates. With convention $C_0$ is true.
>We say that the dimension of a path is undefined whenever there exist some $i$ such that $1\leq i \leq n$ such that 
>$$
>\text{dim}\Big(\text{Pol}\big(\pi_{\mathcal C_{i}}(s, e_{1}\dots e_{i})\big)\Big) <
>\text{dim}\Big(\bigcup_{e}\text{Pol}\big(\pi_{\mathcal C_{i}}(s, e_{1}\dots e_{i-1}e)\big)\Big)
>$$
>Then we say $\text{dim}_{\mathcal A}(\pi_{\mathcal C})=\bot$ otherwise $\text{dim}_{\mathcal A}(\pi_{\mathcal C})=\top$.

In other words. If some of the transition from a state accept only a single valuation of clock while there are other transitions that accept guards containing non singleton intervals then a path containing the former has undefined dimension.

---
# References
[[Timed Automata Alternate Definition]]
