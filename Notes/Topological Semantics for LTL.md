---
tags:
  - Note
  - Incomplete
---
202311181511

Tags : [[Timed Automata]]
# Topological Semantics for LTL
---
The interpretation of [[Linear Temporal Logic|LTL]] formulae happens over finite runs of [[Timed Automata Alternate Definition|Timed Automata]].
The states in a run correspond to the worlds used to define the semantics of *LTL*. Ans we use the function $\mathcal L$ in place of $\sigma$ to give the set of formulas satisfied by $s$.

>[!note] Intuition
>Since only the sequence of states corresponds to the [[Kripke Models|Kripke]] like structures used to give semantics to *LTL*, we can say that given a formula $\varphi$ and a path $\pi$, either all runs of $\pi$ model satisfy $\varphi$ or none of them do.
>Similar to [[Probabilistic Semantics for LTL]], we want to be able to ignore paths and runs that depend on precision of the Timed Automata. For a probabilistic case, we ignore unlikely events, an analogous option would be meager sets. 

So we say that $\mathcal A$ *largely satisfies* $\varphi$ from $s$, or $\mathcal A, s\mid\!\approx_{L} \varphi$ if the set of runs is *large*.

But we also have 
>[!note] Lemma
>Let $\iota : \text{Runs}(\mathcal A,s)\to\text{Runs}(\text R(\mathcal A),\iota(s))$ be the projection map of finite runs from $\mathcal A$  to $\text{R}(\mathcal A)$. Then $\iota$ is continuous. And for every $O\in\mathcal T_\mathcal A$ we have $\text{Int}(\iota(O))$ is non empty.

Using the above lemma we get that
$$
	\mathcal A, s \mid\!\approx \varphi \iff \text{R}(\mathcal A),\iota (s)\mid\!\approx\varphi
$$

---
# References
[[Correspondence of Topological and Probabilistic Semantics for LTL]]