---
tags:
  - Example
---

202402221602

tags : [[Game Theory]]

#  Lemma for Minimax Theorem
---
>[!Theorem] Lemma
>1. We have $\max_{\mathbf{x}}\beta(\mathbf{x})<\min_{\mathbf{y}}\alpha(\mathbf{y})$. For every two [[Mixed Strategies]] $\mathbf{x}$ and $\mathbf{y}$, we have $\beta(\mathbf{x})\leq \mathbf{x}^TM\mathbf{y}\leq\alpha(\mathbf{y})$.
>2. If the pair $(\tilde{\mathbf{x}}, \tilde{\mathbf{y}})$ of mixed strategies form a [[Mixed Nash Equilibrium]] then both of them are worst case optimal.
>3. If both mixed strategies satisfy the condition $\beta(\tilde{\mathbf{x}})=\alpha(\tilde{\mathbf{y}})$ then they form a [[Mixed Nash Equilibrium]]

## Proof
1. For the first point
	1. The first part comes from the definition of $\alpha$ and $\beta$
	2. The second part comes the definition of [[Mixed Nash Equilibrium]] and point 2
2. By point 1, for any $\mathbf{x}$ we have $\beta(\mathbf{x})\leq\alpha(\tilde{\mathbf{y}})$, but we have $\beta(\tilde{\mathbf{x}})=\alpha(\tilde{\mathbf{y}})$ so we have $\tilde{\mathbf{x}}$ is worst case optimal for **Alice**. A symmetric argument works for **Bob**.
3. If $\beta(\tilde{\mathbf{x}})=\alpha(\tilde{\mathbf{y}})$ we have $\beta(\tilde{\mathbf{x}})=\tilde{\mathbf{x}}^TM \tilde{\mathbf{y}} =\alpha(\tilde{\mathbf{y}})$, so they $(\tilde{\mathbf{x}},\tilde{\mathbf{y}})$ is a [[Mixed Nash Equilibrium]] 


---
# Related
[[Mixed Strategies]]
[[Mixed Nash Equilibrium]]
[[Minimax Theorem for Zero-Sum Games]]