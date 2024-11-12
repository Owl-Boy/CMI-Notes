---
tags:
  - Note
  - Incomplete
---
202411021611

Tags : [[Set Theory]]
# Reflection Theorems
---
>[!tip] Idea
>A *Reflection Theorem* says given a property of the class of all sets, it is possible to find a set which "resembles" the class of all sets in terms of the property.

>[!theorem] Reflection Theorem
>Given Any formulas $\phi_1 \dots \phi_{n}$,
>$$ \mathbf{ZF} \vdash \forall \alpha \exists \beta(\phi_{1}\dots \phi_{n}) \text{ are absolutes for } \mathbf{R}(\beta) $$

And the generalized version

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
---
# References
[[Proof for Reflection Theorem]]
[[Constructable Sets]]