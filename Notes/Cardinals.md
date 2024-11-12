---
tags:
  - Note
---
202408291708

Tags : [[Set Theory]]
# Cardinals
---
>[!Definition]
>A *von Neumann Cardinal* is an ordinal $\alpha$ such that $\eta \prec \alpha$ for all $\eta < \alpha$.

Since $\eta < \alpha \to \eta \subseteq \alpha \to \eta \preceq \alpha$ we have that $\alpha$ is not a cardinal iff there is some $\eta$ where $\eta < \alpha$ and $\eta \approx \alpha$. 

This gives us the following properties
- Every Cardinal $\ge \omega$ is a Limit Ordinal.
- Every Natural number is a cardinal.
- If $A$ is a set of cardinals, then $\sup(A)$ is a cardinal.
- $\omega$ is a cardinal.

>[!definition]
>The *Cardinality* of a set $A$ is a cardinal $\kappa$ such that $A \approx \kappa$, denoted by $|A|$

However to prove that such a $\kappa$ exists, we need to well order $A$ which requires Axiom of Choice.

>[!theorem] lemma
>If $A$ can be well ordered, then there exists a bijection $f: A \to \alpha$ for some ordinal $\alpha$, hence $A \approx \alpha$.

>[!theorem] Lemma
>Assume $A, B$ are well orderable sets, then 
>- $|A|$ is a cardinal
>- $A\approx B$ iff $|A| = |B|$
>- $A\preceq  B$ iff $|A| \le |B|$
>- $A\prec B$ iff $|A| < |B|$

1. trivial
2. .
	1. Left to right, bijection exists so $|A| \not< |B|$ because $|B|$ is a cardinal
	2. Right to left, equality just translates to a bijection.
3. .  
	1. Left to right, Injection exists then $|A| \not > |B|$ because $|B|$ is a cardinal
	2. Right to left, If equal, done if not then lift the inclusion of $|A|$ into $|B|$.
4. . 
	1. look at ordinals corresponding to $A$ and $B$.

>[!definition] 
>$A$ is *finite *iff $A$ is well-orderable and $|A| < \omega$.

>[!theorem] 
>Assume $A$ and $B$ are finite with $m = |A|$ and $n=|B|$. Then $A\cup B$ is finite, with $|A\cup B| \leq m+n$  and $A\times B$ is finite with $|A\times B| = m \cdot n$. Also $\text{}^BA$ exists and is finite and $|\text{}^BA| = m^n$ and $\mathcal P(B)$ exists and is finite and $|\mathcal P(B)| = 2^n$.

Induct on $B$ for proof.

---
# References
[[Hereditarily Finite Sets]]
[[Uncountable Cardinalities]]
[[Cardinals Pre-reqs]]
[[Cardinal Arithmetic]]