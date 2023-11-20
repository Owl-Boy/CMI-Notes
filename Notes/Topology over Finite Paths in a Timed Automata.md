---
tags:
  - Note
  - Incomplete
---
202311181311

Tags : [[Timed Automata]], [[Topology]]
# Topology over Finite Paths in a Timed Automata
---
For a [[Timed Automata Alternate Definition|timed automaton]] $\mathcal A$, we define a *basic open set* as a constrained symbolic path $\pi_{\mathcal C}=\pi_{\mathcal C}(s,e_{1}\dots e_{n})$ such that the dimension of $\pi_{\mathcal C}$ is defined and $\text{Pol}(\pi_\mathcal C)$ is open in $\text{Pol}(\pi)$ for the topology induced on it, where $\pi$ is the unconstrained version of the same path.

>[!note] Informal Idea
> We say that a path, i.e a set of runs is open, if its dimension is defined (sort of like treating other paths as discrete points or something, making them not open) and, its open in the polygon corresponding to it.

We write $\mathcal T_{\mathcal A}$ for the topology of $\text{Runs}(\mathcal A,s)$ induced by these sets. i.e The sets defined above, along with the entire space form a *base* for $\mathcal T_\mathcal A$.

>[!example]
>![[Pasted image 20231118135252.png]]
>Here, let $s_0 = (l_0,0)$ be the initial state.
>The *basic (unconstrained) open sets* here are of the form  $\pi(s_{0},(e_{1}e_{2})^*)$ and $\pi(s_{0},e_{1}(e_{2}e_{1})^*)$ 
>An example of a *basic constrained open set* would be $\pi_{\mathcal c}(s_{0},e_{1}e_{2})$ where $\mathcal c = \left\{  \frac{1}{3}<t_{1}< \frac{1}{2} \; ;\;t_{1}+t_{2}>5  \right\}$
>It is also easy to check that the set of paths of the form $\pi(s_{0},(e_{1}e_{2})^*e_{1}e_{3}e_{4}^*)$ is *meager*.

---
# References
- [[Dimension of a Path]]
- [[Timed Automata Alternate Definition]]
- [[Probabilistic Semantics for LTL]]
- [[Topological Space of Paths in a Timed Automata is Baire]]