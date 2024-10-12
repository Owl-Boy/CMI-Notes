---
tags:
  - Note
---
202408311808

Tags : [[Set Theory]]
# Type of a Set and a Relation
---
>[!Theorem] 
>If $R$ well-orders $A$, then there is a unique $\alpha \in \text{ON}$ such that $\langle A; R\rangle \cong \langle \alpha; \in\rangle$.

The uniqueness is trivial from [[Von Neumann Ordinals#^65f4be|this]]. If $a \in A$, let $a \downarrow = \{ x \in A: xRa  \}$. Then $a \downarrow$ is well ordered by $R$ as well. Call $a\in A$ *good* iff the theorem holds for $a\downarrow$: that is, $\langle a \downarrow ; R \rangle \cong \langle \xi;\in \rangle$   for some ordinal $\xi$. Let $G$ be the set of *good* elements of $A$. Let $f$ map elements of $G$ to their isomorphic ordinals. 
- If $G = A$, then $f$ is an isomorphism from $\langle A; R\rangle$ onto $\langle \alpha;\in\rangle$.
- Otherwise, let $e$ be the least element for $A\setminus G$. Then $e\downarrow = G$, and $f$ is an isomorphism from $\langle e\downarrow; R \rangle$ to $\langle \alpha; \in \rangle$, so $e \in G$ which is a contradiction.

>[!definition]
>If $R$ well-orders $A$, then $\text{type}(A; R)$ is the unique $\alpha \in \text{ON}$ such that $\langle A; R\rangle\cong \langle \alpha ; \in\rangle$.

>[!theorem]
>If $R$ well-orders $A$ and $X \subseteq A$ then $R$ well-orders $X$ and $\text{type}(X; R) \leq \text{type}(A; R)$



---
# References
