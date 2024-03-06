---
tags:
  - Example
---

202402281953

tags : [[Automata Theory]], [[Logic]]

#  Closure and Atoms for Büchi construction of LTL formulas
---

For a formula $\varphi$ we will argue for its satisfiability through that of its subformula, a *closure* of a formula would be such a set of relevant formulae.

>[!definition] Fischer-Ladner Closure
>Given an *LTL* formula $\alpha$ the closure $\text{Cl}(\alpha)$ is the smallest set of formulas such that:
>- $\alpha\in \text{Cl}'(\alpha)$
>- If $\lnot \beta\in \text{Cl}'(\alpha)$ then $\beta\in \text{Cl}'(\alpha)$
>- If $\beta \land \gamma\in \text{Cl}'(\alpha)$ then $\beta,\gamma \in \text{Cl}'(\alpha)$
>- If $\bigcirc \beta \in \text{Cl}'(\alpha)$ then $\beta\in \text{Cl}'(\alpha)$
>- If $\beta\ \mathcal U\ \gamma\in \text{Cl}'(\alpha)$ then $\beta,\gamma,\bigcirc(\beta\ \mathcal U\ \gamma)\in \text{Cl}'(\alpha)$
>
>And $\text{Cl}(\alpha)=\text{Cl}'(\alpha)\cup \{ \lnot\beta\;|\;\beta\in\text{Cl}'(\alpha)\}$ where we identify $\beta$ and $\lnot\lnot\beta$.

Now that we have a more expressive set to work with instead of just propositions, we can construct an automata for $\varphi$ by taking $2^{\text{Cl}(\varphi)}$ as the alphabet, but it contains a ton of inconsistent states, say which contain both a formula and its negation. So we find a better subset of $2^{\text{Cl}(\varphi)}$ to work with which will be called *Atoms*

>[!definition] Atoms
>A set $A\in \text{Cl}(\alpha)$ for some $\alpha$ is called an atom if :=
>- $\forall \beta\in \text{Cl}(\alpha)$ we have $\beta \in A$ iff $\lnot \beta \not\in A$
>- $\forall \beta \lor \gamma \in \text{Cl}(\alpha)$ we have $\beta \lor \gamma \in A$ iff $\beta\in A$ or $\gamma\in A$
>- $\forall \beta\ \mathcal U \gamma \in \text{Cl}(\alpha)$ we have $\gamma \in A$ or $\beta, \bigcirc(\beta\ \mathcal U\ \gamma)\in A$
>
>There are precisely the maximal subsets of the closure that are both propositionally and temporally consistent.
>
>Let $\mathcal {AT}$ be the set of all *Atoms*

Atoms help us with two things
- That subsets of the closure that aren't atoms are either inconsistent in some manner, or can be completed to get one or more Atoms, hence are redundant
- The temporal operators used in an atoms tells us its relations with other atoms, which will be discussed more in [[Büchi Automata for Linear Temporal Logic]]

---
# Related
[[Linear Temporal Logic]]
[[Büchi Automata|Buchi Automata]]
[[Büchi Automata for Linear Temporal Logic]]