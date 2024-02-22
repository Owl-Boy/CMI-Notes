---
tags:
  - Note
  - Incomplete
---
202402161402

Tags : [[Combinatorial Optimisation]]
# Separation Oracle for perfect matching LP
---
> [!question] Motivation
> We have the [[Ellipsoid Algorithm]] for solving an LP. In the algorithm we assume that we can check if all constraints are satisfied by a given point, or get the violated constraint easily. But there could be exponentially many constraints e.g. in the perfect matching LP. Thus we require a *Separation Oracle*, as described below, which we will construct.

**Separation Oracle:** An algorithm which takes a point $z$ as input and either outputs "$z$ is feasible" or outputs a violated constraint.

## LP
---
$|V|=n, |E|=m$
$\sum\limits_{e\sim v}x_{e}=1\quad\forall v\in V$
$\sum\limits_{e\in\delta(S)}x_{e}\geq 1\quad\forall S\subseteq V,|S|\text{ odd},|S|\geq 3,|V\setminus S|\geq 3,\forall e\in E$

**Goal:** Given a point $z\in\mathbb{R}^{n}$ determine if $z$ satisfies all the constraints, else output a violated constraint.

---
for some reason we do the following:(??)

The max flow algorithm finds a max-flow from $s$ to $t$, and hence a min-cut between $s$ and $t$.
Choose a vertex as $s$, and for each choice of $t\in V\setminus \{ s \}$ find an $s-t$ mincut. Output the mincut among those.

Assume $n$ even. So $|S|$ odd $\iff$ $|V\setminus S|$ odd.
$S$ be the mincut in $G$, $|S|$ is even.
$S^{*}$ be the min odd cut in $G$.

**Obs.:** Either $|S\cap S^{*}|$ is odd or $|(V\setminus S)\cap S^{*}|$ is odd.
WLOG let $|S\cap S^{*}|$ be odd.
For $A\subseteq V$ $z(\delta(A))\stackrel{\Delta}{=}$







---
# References
[[LP algorithm for general Perfect Matching]]
[[Linear Programming]]