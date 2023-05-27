202304041204

Type : #Note
Tags : [[Topology]]

---
# Retractions
```ad-note
title:
For $A \subseteq X$, a **retraction** $r : X \to A$ is a continuous map such that $r(a) = a \ \forall \ a \in A$. If such an $r$ exists, we say that $A$ is a **retract** of $X$.
```

### Lemma:
```ad-note
title:
If $r : X \to A$ is a retraction, the homomorphism of fundamental groups $i_{*} : \Pi_{1}(A,a_{0}) \to \Pi_{1}(X,a_{0})$ induced by the inclusion $i:A \hookrightarrow X$ is an injective homomorphism.
```
##### Proof:
We know that $r \circ i = id_{A}$ and so, $r_{*}\circ i_{*} = id_{\Pi_{1}(A,a_{0})}$. This gives that $i_{*}$ is injective. Also gives that $r_{*}$ is surjective.

### Lemma:
```ad-note
title:
There is no retraction of $B^{2}$ to $S ^{1}$. Here, $B^{2}$ denotes the closed unit disk $\{ (x,y) \mid \ x ^{2}+y^{2} \le 1 \} \subset \mathbb{R}^{2}$.
```
##### Proof:
Assume $r:B^{2} \to S ^{1}$ was a retraction then $i_{*}:  \Pi_{1}(S ^{1},b_{0}) \to \Pi_{1}(B^{2},b_{0})$ must be injective but that's impossible since $\Pi_{1}(S_{1},b_{0}) = \mathbb{Z}$ and $\Pi_{1}(B^{2},b_{0}) = \{ 0 \}$.


---
# References
[[Fundamental Group]]