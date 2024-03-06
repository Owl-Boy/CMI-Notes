---
tags:
  - Note
  - Incomplete
---
202402210902

Tags : [[Infinite State Verification]]
# Communication Free Petri-Net
---
>[!idea] Simpler Model
>This is a restricted version of a [[Petri Net]] where a transition is only allowed to consume at most 1 token in total (which also means that it can only take it from at most 1 place).
>It can put multiple tokens in multiple places, no restriction on that.

>[!definition]
>Let 
>$$\mathcal N = \langle \mathcal P, T, \lambda, \text{in}, \text{out}\rangle $$
>The following will be used for structurally talking about the Petri Net. Given a Petri Net $\mathcal N$, and $T'\subseteq T$ , we define $\mathcal N(T')$ as the Petri Net restricted to $T'$.

>[!tldr] Goal
> The goal is to prove reachability properties for this model, and use that to talk about presburger arithmetic and talk about parikh space for push down systems

---
>[!theorem]
>There is a run $\sigma\in T^*$ such that $M_0\xrightarrow{\sigma}N$ iff
>1. For every place $p\in P$, we have $M_0(p)+\sum_{t\in T}(\text{out}(t)-\text{in}(t))\cdot \Pi_{\sigma}(t)\ge {0}$
>2. Restricting the petri net to just the transitions that are fires gives us exactly the set of states that will contain a resource at some point in the run.

For the proof of the theorem, left to right is trivial. for right to left, proving point 1 is easy, for point 2 we can induct of the size of the run.

---
# References
