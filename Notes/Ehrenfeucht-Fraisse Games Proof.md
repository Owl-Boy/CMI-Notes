---
tags:
  - Note
---
202310201210

Tags : [[Logic]]

# Ehrenfeucht-Fraïssé Games Proofs
---
// stuff from last lecture: definition etc

```ad-info
title:Lemma: TFAE
1. $(A,\overline{a})\equiv_{k}(B,\overline{b})$.
2. $(A,\overline{a}),(B,\overline{b})$ agree on FO$[k]$.

$\overline{a}$ is an $m-$tuple.
```

---

FO$[0]$ has only terms and formulas without any quantifiers
We have $m$ free variables.
$N=|R|.m^{j}+m^{2}$
The number of FO formulas will be infinite. We want to count the number of FO formulas up to logical equivalence.

Because there are no quantifiers, we can go to propositional logic for inspiration.

In propositional logic, the number of formulas we could have is $2^{2^{n}}$. We got that by observing that each partition of the set of valuations gives a unique (up to logical equivalence) formula. The size of the set of valuations is $2^{n}$, hence the number of partitions of the set is $2^{2^{n}}$, as claimed.

Now, drawing a parallel to FOL, we observe that an FO formula $\varphi$ can't distinguish between two interpretations $\mathcal{I}_{1}$ and $\mathcal{I}_{2}$, $\mathcal{I}_{1}\vDash\varphi$ iff $\mathcal{I}_{2}\vDash\varphi$. In the set of all interpretations, we have $2^{N}$(why) equivalence classes. Any FO formula will partition this set of equivalence classes (there's a bijection). Thus there are $2^{2^{N}}$ FO$[0]$ formulas.

---
Up to logical equivalence FO$[0]$ has only finitely many formulas on $m$ free variables.
We will prove this for FO$[k]$ by induction on $k$.
Ind. hypo.: $\varphi$ is a FO$[k]$ formula on $m+1$ variables.
Any FO$[k+1]$ formula in $m$ free variables is a Boolean combination of formulas of the form $\exists x\ \varphi$ or $\forall x\ \varphi$, where $\varphi$ is a FO$[j]$ formula for $j\leq k$, in $m+1$ free variables.

---
Going back to graphs with all this newly learnt knowledge
If we have only FO[0] formulas, we can only talk about the vertices that are in front of us (in the induced subgraph), and the edges between them.
If we have only FO[1] formulas, we can only talk about the vertices and their plus ones, i.e. for the vertices we have, we can only talk about edges among them and 2-length paths among them (so we can talk about 1-radius balls around those vertices).
Similarly for a general $k$.

---
Formalising that stuff^
Given an $m-$ tuple $\overline{a}$ of elements in a structure $A$, the *rank-$k$ $m-$type* of $\overline{a}$ in $A$ is the set $\{ \varphi \in FO[k]\ |\ A,\overline{a}\vDash\varphi \}$ 

---
# References
[[First Order Logic]]
[[Even is not FO-definable]]
