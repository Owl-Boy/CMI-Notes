---
tags:
  - Note
  - Incomplete
---
202409302309

Tags : [[Set Theory]]
# Relative Strength of ZF- and ZF
---
>[!tip] Goal
>The goal here is to show that $\text{ZF}^-$ and $\text{ZF}$ are proof theoretically equivalent.

>[!theorem] $ZF^--P$ 
>For any class $M$:
>1. If $M$ is transitive, then the axiom of extensionality holds in $M$
>2. If $M \in \text{WF}$ then the foundation axiom holds in $M$
>3. If $\forall z \in M, \forall y \subseteq z, [y\in M]$ then the comprehension axiom holds in $M$
>4. $\forall x, y\in M, \{ x, y \}\in M$ then pairing holds in $M$
>5. If $\forall \mathcal  F\in M\left[ \bigcup \mathcal F \in M\right]$, then the union axiom holds in $M$
>6. Assume $M$ is transitive for all functions $f$: If $\text{dom}(f)\in M$ and $\text{ran}(f) \subseteq M$ then $\text{ran}(f)\in M$ Then replacement axiom holds in $M$.

1. If $M$ is transitive then for any $x, y\in M$, all their elements are also in $M$.
2. By definition
3. We will get a why by comprehension and by the restriction on $M$, we are done
4. trivially
5. trivially
6. By restriction on $M$ we directly get the result.

>[!theorem] Corollary
>Axioms $1,2,3,4,5,6$ hold in $\text{WF}$.

>[!theorem] Corollary
>$ZF^-, R(\gamma) \vDash$ axoims $1,2,3,4,5$ whenever $\gamma$ is a limit ordinal. $R(\gamma)\vDash$ axiom 6 if $\gamma$ is regular.

First 5 are trivial, if $\gamma$ is regular then the condition in theorem is satisfied by the definition of regularity and $R(\gamma)$.

>[!theorem] In $\text{ZF}^-$, if $M$ is transitive, then power set theorem holds.
>$$
>\forall x \in M, \mathcal P(M)\cap M \in M \to \text{ The Power Set axoim holds in }M.
>$$
>If comprehension exists, the other side also holds true.

We just take $y$ to be $\mathcal P(x)\cap M$. With comprehension we just build the set $\mathcal P(x)\cap M = \{ z\in y : (z\subseteq x)^M\}\in M$

>[!theorem] Corollary
>Power set holds in $\text{WF}$ and $R(\gamma)$ for any limit ordinal $\gamma$.

>[!theorem] $(\text{ZF}^--P)$ Infinity and choice.
>Assuming Axioms of Extensionality, Comprehension, Pairing and Union hold in $M$ and it is transitive
>- The Axiom of Infinity holds in $M$ if $\omega \in M$
>- Axiom of Choice holds in $M$ iff every disjoint family of sets has a choice set.

- If we have $\omega \in M$, then by transitivity we have $n\in M$ for all $n\in \omega$, specifically $\emptyset\in \omega$ and $S(n)\in M$ for all $n\in \omega$, hence the closure of $\{ \emptyset \}$ under $S=\omega$.
- Given a disjoint family of sets, get their choice set using the axiom of choice. Apply the function $f : x\mapsto \{ x \}$ on it. Each one of them is in $M$, the union on the set gives something in $M$ hence $C$ is in $M$.

>[!theorem] Dropping foundation
> All of the following theories
> - $\text{ZF}$
> - $\text{ZFC}$
> - $\text{ZF-P}$
> - $\text{ZFC-P}$
> 
> Are proof theoretically equivalent to themselves without the theory of foundation.


---
# References
