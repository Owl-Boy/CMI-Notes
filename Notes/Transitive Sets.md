---
tags:
  - Note
---
202408101608

Tags : [[Set Theory]]
# Transitive SetsVon Neumann Ordinals
---
>[!definition]
>A set $z$ is **Transitive** iff, every element of $z$ is a subset of $z$

>[!example]
>- $\emptyset$
>- $\{\emptyset\}$
>- $\{ \emptyset, \{ \emptyset \}, \{  \{ \emptyset \} \} \}$

---

>[!theorem] 
>Assuming [[ZFC and family#^df7c78|Axiom of Foundation]], every non empty transitive set contains the empty set and every non-empty, non-singleton transitive set contains $\{ \emptyset \}$.

Given a non-empty transitive set $z$, by the axiom of foundation, there exists an element $x \in z$ such that $x \cap z = \emptyset$. But since $x \subseteq z$, $x = \emptyset$.

Given a non-empty, non-singleton transitive set $w$, we know that $\emptyset \in w$. let $w' = w \setminus \emptyset$.

By the axiom of foundation $w'$ contains an element $y$ such that $w' \cap y = \emptyset$. 

$y\ne \emptyset \implies \exists p\in y$. But $y$ is a subset of $w$, therefore, if $p\ne \emptyset$ then $p \in w'\cap y$, therefore $p = \emptyset$. 


---
# References
