---
tags:
  - Note
---
202409030609 ^9775e7

Tags : [[Set Theory]]
# Uncountable Cardinalities
---
If we add the [[ZFC and family#^44e52f|Power Set Axiom]] to analyse [[Cardinals]], then we are able to construct *Uncountable Cardinals*.

If we assume Axiom of Choice, then every set can be well ordered and $|\mathcal P(\omega)|$ is an uncountable ordinal, but we can prove the existence of uncountable ordinals without it.

---

>[!Theorem] Hartogs, 1915
>For every set $A$, there is a cardinal $\kappa$ such that $\kappa \not\preceq A$.

^5df0be

***Proof:***
Let $W$ be the set of pairs $\langle X, R\rangle\in \mathcal P(A) \times \mathcal P(A \times A)$ such that $R$ **well-orders** $X$. So $W$ is the set of all well orderings of all subsets of $A$. $\alpha \le A \iff \alpha = \text{type}(X; R)$ for some $X$ and $R$. So we apply [[ZFC and family#^c2b9a6|Replacement Axiom]] on $W$ and let $\kappa = \text{sup} \{ \text{type}(X; R)+1 : \langle X, R \rangle \in W\}$. Now, forall $\alpha \le A$, we get $\kappa > \alpha$, so $\kappa \not\preceq A$.

>[!definition] Infinite Cardinalities
>By recursion on $\xi$ we define:
>- $\aleph_0 = \omega_{0}=\omega$
>- $\aleph_{\xi+1} = \omega_{\xi+1} = (\aleph_{\xi})^+$
>- $\aleph_{\eta}=\omega_{\eta}=\text{sup}\{ \aleph_{\xi} : \xi < \eta\}$ when $\eta$ is a limit ordinal

>[!theorem]
>- ${}^A{2} \approx \mathcal P(A)$
>- ${}^C(^B A) \approx {}^{C\times B}A$
>- ${}^{(B \sqcup C)} A\approx{}^BA \times {}^CA$

trivial

>[!theorem]
>If $\alpha \ge \omega$ then $|\alpha \times \alpha| = |\alpha|$. Hence if $\kappa \ge \omega$ is a cardinal then $|\kappa \times \kappa| = \kappa$

For that we define $(\xi_{1},\xi_{2}) \triangleleft (\eta_{1}, \eta)$ if $\max(\xi_{1}, \xi_{2}) < \max(\eta_{1},\eta_{2})$ if both are the same, then apply lexicographical order. This is a well order on $\text{ON}$.

Now we show that $\text{type}(\kappa \times \kappa ; \triangleleft) = \kappa$.
Contradiction FTSOC let $\kappa$ be the minimum such that the above does not hold, $\delta = \text{type}(\kappa \times \kappa, \triangleleft) \ne \kappa$.

If $\alpha < \kappa$, is infinite, then $|\alpha \times \alpha| = |\alpha|$ as $\kappa$ is the minimum cardinal for which the assumption holds.

- Let $\delta < \kappa$, we have injection from $\kappa \times \kappa$ to $\kappa$ and vice versa too, so we are done.
- Let $\delta > \kappa$, let $F$ be the bijection from $\delta$ to $\kappa \times \kappa$ and let $(\xi_{1}, \xi_{2})$ be $F(\kappa)$. Let $\alpha = \max(\xi_1, \xi_2)+1$ and we have $F(\kappa) \triangleleft \alpha \times\alpha$ which is a contradiction.  


---
# References
