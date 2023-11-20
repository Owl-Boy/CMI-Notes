---
tags:
  - Note
  - Incomplete
---
202311162211

Tags : [[Timed Automata]]
# Machinery for Probabilistic Semantics for Timed Automata
---

>[!hint] Motivation
>Here we give Timed Automata as a model to give probabilistic interpretation to delays so that unlikely events will happen with probability $0$

We fix an automata $\mathcal A =\langle L,X,E, \mathcal I, \mathcal L\rangle$ which we assume to be non blocking.
For every state $s$ we define a *probability measure* $\mu_s$ over $\mathbb R_+$ with the following requirements
- $\mu_s(I(s)) = \mu_s(\mathbb R_+)=1$
	- Intuitively it means that the probability of taking some transition is $1$. This is possible because we assume that the timed automata is non-blocking
- We use $\lambda$ for the Lebesgue measure, if $\lambda(I(s))>0$ then $\mu_s$ is equivalent to $\lambda$, otherwise $\mu_s$ is the uniform distribution over the set of points in $I(s)$
- For every state $s$ we also assume a probability distribution $p_s$ over the edges such that $p_s(e)>0$ iff $e$ is enabled in $s$.

>[!example]
> - Uniform Distribution over $I(s)$ if it is finite.
> - Lebesgue Measure normalised to have a probability measure if $I(s)$ is a finite set of bounded intervals.
> - Exponential distribution if $I(s)$ contains an unbounded interval.

Given that we have the above machinery, we can define a [[Probability Measure over Finite Paths in a Timed Automata]].

---
# References
- [[Probability Measure over Finite Paths in a Timed Automata]]
- [[Timed Automata Alternate Definition]]