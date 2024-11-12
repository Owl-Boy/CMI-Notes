---
tags:
  - Note
---
202411031211

Tags : [[Set Theory]]
# Proof for Reflection Theorem
---
>[!Theorem] Supporting Lemma
>Let $M$ and $N$ be classes with $M \subsetneq N$. Let $\phi_{1}\dots \phi_{n}$ be a subformula closed list of formulas, then the following are equivalent
>- $\phi_{1}\dots \phi_{n}$ are absolute for $M, N$.
>- Whenever $\phi_{i}$ is of the form $\exists x \phi_{j}(x, y_{1}\dots y_{l})$ with $x,y_{i}$ being the free variables of $\phi_{j}$,
>  $$ \forall y_{1}\dots y_{l}\in M(\exists x\in N\phi^N_{j}(x, y_{1}\dots y_{l}) \to \exists x \in M \phi^N_{j}(x, y_{1} \dots y_{l}))$$

1 -> 2 is by definition of absoluteness
2 -> 1 one can check by induction on the length of the formula, which is trivial to check for atomic formulas, conjunctions and negations, for existential quantifiers

$$
\begin{align}
\phi_{i}^M(y_{1}\dots y_{l}) &\leftrightarrow \exists x\in M \phi^M(x, y_{1}\dots y_{l}) \leftrightarrow  \exists x \in M \phi_{j}^N(x, y_{1}\dots y_{l}) \\
&\leftrightarrow \exists x\in N \phi^N(x, y_{1}\dots y_{l}) \leftrightarrow \phi_{i}^N(y_{1}\dots y_{l})
\end{align}
$$

>[!Theorem] Generalized Version (ZF)
>Let $Z$ be a class and for each $\alpha, Z(\alpha)$ is a set and assume
>- $\alpha<\beta \to Z(\alpha) \subseteq Z(\beta)$
>- If $\gamma$ is a limit ordinal, $Z(\gamma) = \bigcup_{\alpha<\gamma}Z(\alpha)$
>- $Z = \bigcup_{\alpha\in \mathbf{ON}}Z(\alpha)$
>
>Then for any formulas $\phi_{1}\dots \phi_{n}$,
>$$
>\forall \alpha \exists \beta>\alpha (\phi_{1}, \dots \phi_{n} \text{ are absolute for }Z(\beta), Z)
>$$

Using the previous lemma, we let $N=Z$ and we find a $\beta$ such that $Z(\beta)$ will behave as $M$. We also assume that the list of formulas as subformula closed.

For each $i=1..n$, define a function $F_{i} : \text{ON}\to \text{ON}$ as follows. If $\phi_{i}$ is of the form $\exists x \phi_{j}(x, y_{1}\dots y_{l})$, let $G_{i}(y_{1}\dots y_{l})$ be $0$ if $\lnot \exists x \in Z\phi_{j}^Z(x, y_{1}\dots y_{l})$, and the least $\eta$ such that 
$$
\exists x \in Z(\eta)\phi_{j}^Z(x, y_{1}\dots y_{l})
$$
if $\exists x\in Z \phi^Z_{j}(z, y_{1}\dots y_{l})$.
Now we define 
$$
F_{i}(\xi)= \sup \{ G_{i}(y_{1}\dots y_{l}) : y_{1}, \dots y_{l} \in Z(\xi)\}
$$
If $\phi_{1}$ is not existentially quantified, then $F_{i}=\mathbf{0}$.

Supermum is well defined because of replacement axiom.

By the lemma, if $\beta$ is a limit ordinal and for each $i, \forall \xi<\beta(F_{i}(\xi)<\beta)$, then $\phi_{1}\dots \phi_{n}$ will be absolute for $Z_{\beta}, Z$. Fix $\alpha$, we show how to find such a $\beta>\alpha$. Let $\beta_{0}=\alpha$ and let $\beta_{p+1}$ be the largest of 
$$
\beta_{p}+1, F_{1}(\beta_{p}) \dots F_{n}(\beta_{p})
$$
Now let $\beta= \sup \{ \beta_{p} : p \in \omega \}$.

Since $F_{i}$ is an increasing function so for each $\xi<\beta$
$$
\xi<\beta_{p} \to F_{i}(\xi)\leq F_{i}(\beta_{p}) \leq \beta_{p+1} < \beta
$$

Hence we are done.

>[!theorem] Reflection Theorem
>Given Any formulas $\phi_1 \dots \phi_{n}$,
>$$ \mathbf{ZF} \vdash \forall \alpha \exists \beta(\phi_{1}\dots \phi_{n}) \text{ are absolutes for } \mathbf{R}(\beta) $$


---
# References
