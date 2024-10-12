---
tags:
  - Note
  - Incomplete
---
202409120109

Tags : [[Set Theory]]
# Axiom of Choice and its Variants
---
### Equivalences

1. There exists a choice set for every family $\mathcal F$ of non empty disjoint sets.
2. Every family of Non-empty sets has a choice function
3. Every set can be well ordered
4. $\forall xy(x \preceq y \lor y\preceq x)$ 
5. Tukey's Lemma
6. The Hausdorff Maximal Principle 
7. Zorn's Lemma

---
### Equivalence Proof
For $2 \to 1$:
Given a disjoint family $\mathcal F$ of non-empty sets. If $g$ is a choice function for $F$ then $C : \{ g(x) : x \in \mathcal F \}$ is a choice set for $\mathcal F$.

For $1 \to 2$:
Given any family $\mathcal F$ define $\mathcal F^* = \{ \{ x \} \times x:  x \in \mathcal F\}$, then $\mathcal F^*$, then $C$ is the set of ordred pairs and is a function $\text{dom}C = F$, and $C$ is a choice function of $\mathcal F$.

For $3 \to 2$
If $R$ well orders $\cup \mathcal F$, we can define a choice function $g$ by letting $g(x)$ be the $R$-least elements of $x$.

For $3 \to 4$
If $x$ and $y$ can be well ordered then $|x|$ and $|y|$ are cardinals and by trichotomy of cadinals we have $|x| \le |y|$ or $|y|\le |x|$, hence there are injection in at least 1 direction.

For $4 \to 3$
By [[Uncountable Cardinalities#^5df0be|Hartogs Lemma]] we get that given a set $A$ there exists $\kappa$ such that $\kappa\not\preceq A$, by $4$ we have $A\preceq \kappa$, so there is an injection from $A \to \kappa$ hence $A$ can be well orderd. The lemma uses the power set axiom.

For $2\to 3$
The idea is to pick elements of a set one by one and taking that order as the well order.
Consider a set $A$ and define $g$ to be a choice function on $\mathcal P \setminus \{\emptyset\}$.
Let $\kappa = A^+$ and define $f:\kappa \to A \cup \{S\}$ such that $S\not\in A$.

Now we define $f(\alpha) = g(A\setminus \{ f(\eta): \eta<\alpha \})$ if $g$ is defined otherwise $f(\alpha) = S$ 

let $\alpha$ be the least ordinal such that $f(\alpha) = S$, then $f$ restricted to $\alpha$ is a bijection from an ordinal to a set which gives it a well order. 

For $3 \to 6$
Let $\triangleleft$ be a strict partial order on $A$. Apply $3$ to get a well order $\{ a_{\alpha} | \alpha < \kappa \}$ on $A$. Recursively define $C\subseteq A$ so that $a_\alpha \in C$ iff $\{ a_{\alpha} \} \cup \{ a_\xi : \xi < \alpha\}$ is a chain. $C$ is a maximal chain.

For $6 \to 7$
Fix $a \in A$ and let $A'= \{ x \in a : x \geq a \}$. Let $C \subseteq A'$ be a maximal chain. Fix $b\in A'$ such that $x \leq b$ for all $x \in C$ then $b$ is a maximal element of $A$ and $b \geq a$

For $7 \to 5$
Let $x\in \mathcal F$, let $\mathcal F' = {Y \in \mathcal F : X \subseteq Y }$, Then a maximal in $\mathcal F'$ is a maximal in $\mathcal F$.

For $5\to 3$
Fix a set $A$ and then by [[Uncountable Cardinalities#^5df0be|Hartogs]] we get a $\kappa$ such that $\kappa \not\le A$. Let $\mathcal F \in \{f: \mathcal P(\kappa \times A) \}$ such that $f$ is an injection from the subset of $\kappa$ into $\alpha$. Then $\mathcal F$ has finite character so by tuckey's lemma, there is a maximal $f$.
- If $\text{ran}(f) = A$ then we well order $A$ by defining $f(\eta) < f(\zeta)$ if $\eta < \zeta$
- Otherwise, fix $a \in A \setminus \text{ran}(f)$ and fix $\alpha \in \kappa\setminus \text{dom}(f)$, then $f\cup \{(\alpha, a)\}$ contradicts maximality of $f$. 

---
# References
