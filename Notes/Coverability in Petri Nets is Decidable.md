---
tags:
  - Note
  - Incomplete
aliases:
  - Karp-Miller Trees
---
202402091602

Tags : [[Infinite State Verification]]
# Coverability in Petri Nets is Decidable
---
>[!Theorem] Coverability in Petri Nets is Decidable
>Given a Petri Net $\mathcal P$ and two *markings* $M_0$ and $M_f$, finding whether there exits a run $\sigma$ on $\mathcal P$ such that $M_{0}\rightsquigarrow^\sigma M_{f}'$ such that $M_{f}' \ge M_f$  

>[!tip] Intuition
>The proof for the above theorem is a graph search where the nodes are markings and two markings are connected by transitions.
>But the space of markings is $\mathbb N^k$ if $\mathcal P$ has $k$ states. So we quotient sets to get a *finite search space*.

## Karp-Miller Trees Construction
>[!idea] $\omega$-Markings
> Given a marking $M$ of a Petri-net, we can take a sequence of transitions $\sigma$ that takes us to the transition $M'> M$, that is, $\forall x\in[1\dots k],\; M'(i)\ge M(i)$ and $\exists x,\; M'(x) > M(x)$. Then we can replace all components of $M'$ that are more than $M$ with $\omega$ such that $\forall n\in \mathbb N,\;\omega > n$.
> This step represents that $\sigma$ can be used to pump the values indefinitely.

The construction of the *Karp-Miller Trees* is as follows
- We start with the node $M_0$
- For each configuration $M$ that $M'$ can go to. Where $M'$ is **leaf** in the tree
	- If $M$ is already there in the graph as a non leaf, we connect $M'$ to $M$.
	- If there exists a marking $N$ in any of the directed paths from $M_0$ to $M$ such that $M\geq N$, then we add the node $N'$ as a **child** of $M'$ where $$\forall i\in [1\dots k],\;\;N'(i)=\begin{cases}N(i) & N(i)=M(i) \\ \omega &\text{otherwise}\end{cases}$$
	- Otherwise we add $M$ as a **child** of $M'$ in the graph.

>[!warning] Abuse of Notation
>The *Karp-Miller Tree* is not really a tree as there are back edges.
>So in this case a **leaf** is a node that has $0$ out-degree.

---
# References
[[Properties of Karp-Miller Trees]]