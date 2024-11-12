---
tags:
  - Note
---
202408101608

Tags : [[Set Theory]]
# Von Neumann Ordinals
---
>[!definition] 
>$z$ is a **Von Neumann Ordinal** iff $z$ is a transitive set and $z$ is well-ordered by $\in$.

---
## Properties

- Assuming [[ZFC and family#^df7c78|Axiom of Foundation]], $z$ is a Von Neumann Ordinal iff $z$ is transitive and $\in$ total-orders $z$.
- If $x$ is an ordinal, then $x \not\in x$ as it breaks irreflexivity of $\in$.
- If $x$ is an ordinal, so is $S(x)$.

>[!definition] Notation
>- $\langle0\rangle = \emptyset$
>- $\langle n \rangle = \langle n-1 \rangle \cup \{  \langle n - 1\rangle \}$

- $\forall \alpha \in \text{ON}: \alpha \subseteq \beta \leftrightarrow \alpha \in \beta \lor \alpha = \beta$ 
- $\text{ON}$ is well-ordered by $\in$
- $\text{ON}$ is a proper class
	- Otherwise $\text{ON}$ would be an ordinal and $\text{ON} \in \text{ON}$ which is a contradiction.
- If $a, b \in\text{ON}$, then $a \cup b = \max (a, b)$ and $a \cap b = \min (a, b)$

>[!definition]
>- An ordinal $\beta$ is called a *Successor Ordinal* iff $\beta = S(\alpha)$ for some ordinal $\alpha$.
>- An ordinal $\beta$is a limit ordinal iff $\beta \ne 0$ and is not a successor ordinal.
>- An ordinal $\beta$ is a *Natural number* iff $\beta = 0$ or it is the successor of another natural number. 
>- An ordinal $\beta$ if "finite" iff $beta \preceq n$ for any natural number $n$.

- Only Natural numbers are finite
	- This is because if $beta >= \omega$ and is finite, there exists an injection $f$ to some $n$, restrict $f$ to $S(n)$ which gives an injection from $S(n)$ to $n$.

- If $f: \alpha \xrightarrow[\text{onto}]{1-1} \beta$ is an isomorphism from $\langle\alpha;< \rangle$ to $\langle \beta ; < \rangle$ then $f$ is identity map and hence $\alpha = \beta$ ^65f4be
	- If $f$ is not identity, then consider the smallest element for which $x \ne f(x)$, that is a contradiction/

---
# References
[[Transitive Sets]]
[[Cardinals]]
[[Type of a Set and a Relation]]