202302121802

Type : #Note
Tags : [[Topology]]

---
# Tube Lemma
```ad-note
title: Theorem
$X$ and $Y$ topological spaces with $Y$ [[Compactness|compact]]. Let $p \in X$. If $N \subset X \times Y$ is open s.t. $\{p\} \times Y \subset N$ then there is a nbhd $U\subset X$ of $p$ s.t. $U \times Y \subset N$.
```

#### Proof:
For each $(p,q)\in X \times Y$ we have $(p,q) \in \{p\}\times Y \subset N$. Since $N$ is open, we have a basis element $V_q$ s.t. $(p,q) \in U_q\times V_q\subset N$. This is a cover of $\{p\}\times Y$ and since $Y$ is [[Compactness|cpt]], this has a finite subcover. Hence $\bigcap U_{q_i}\times Y$ contains $\{p\}\times Y$. So $U = \bigcap U_{q_i}.\square$

---
# Related Problems

---
# References
