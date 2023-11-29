---
tags:
  - Example
---

202311291813

tags : [[Logic]]

#  Los-Vaught Test
---
We say that a theory $T$ is $\kappa$-categorical for some infinte cardinal $\kappa$ iff all models of size $\kappa$ are isomorphic.

>[!note] Theorem
>Let $T$ be a theory in a countable language. Assume that $T$ has no finite models.
>- If $T$ is $\aleph_0$ categorical, then $T$ is complete
>- If $T$ is $\kappa$-categoriacal, for some uncountable cardinal $\kappa$, then $T$ is complete.

## Proof
Assume there are no finite models of $T$.

**FTSOC:** Let $T$ be $\kappa$-categorical for some uncountable $\kappa$ and be incomplete.
Find $\phi$ such that $T\cup\{\phi\}$ and $T\cup\{\lnot\phi\}$

By the [[Upward Löwenheim-Skolem Theorem]], we have that, there exits $\kappa$ models of both $T\cup\{\phi\}$ and $T\cup\{\lnot\phi\}$.
This is a contradiction as all $\kappa$ models are isomorphic.

---
# Related
[[Natural Numbers with Successor Function is Complete]]