202301161101

Type : #Note
Tags : [[Topology]]

---
# Subspace Topology
### Definition 
```ad-note
title:
Let $X$ be a topo space, and $Y \subset X$, $\tau_Y = \{U \cap Y: U \in \tau_X\}.$
This topology is said to be _inherited_ from $X$ and is called the **subspace topology**.
```
We can check that this is indeed a topology.

#### Lemma:
If $\mathcal{B}$ is a basis for $\tau_X$, then $\mathcal{B}_Y = \{B \cap Y : B \in\mathcal{B}\}$ is a basis on $Y$ for $\tau_Y$. 

Proof:
1. Covering : $\bigcup \limits_{c \in \mathcal{B}_Y} c = \bigcup \limits_{B \in\mathcal{B}} \cap Y = Y$
2. Gluing: $C_1,C_2 \in \mathcal{B}_Y$, $C_1 \cap C_2 = B_1 \cap B_2 \cap Y$. For any $x \in B_1 \cap B_2 \cap Y$, there is a $B_3 \in \mathcal{B}$ such that $x \in B_3 \subset B_1 \cap B_2$. Therefore, $x \in B_3 \cap Y = C_3 \in \mathcal{B}_Y$.  

### Examples
1. Any subspace of a discrete space is discrete.
2. $Y = (a,b) \subset \mathbb{R}$. $\mathcal{B}_{(a,b)} = \{(c,d) : a\le c < d\le b\}$.
3. $Y = [a,b) \subset \mathbb{R}$. $\mathcal{B}_Y = \{[a,d),(c,d) : a<c<d \le b \}$. 
4. $Y = \mathbb{Z} \subset X = \mathbb{R}$. For any $n\in \mathbb{Z}, \{n\} = (n-1/2,n+1/2) \cap \mathbb{Z}$. discrete subspace.
5. $Y = \{1/n : n \in \mathbb{Z}\} \cup \{0\} \subset X = \mathbb{R}$  not discrete topo.
6. $X = \mathbb{R}_{\ell} \supset [a,b] = Y$. $\{b\}$  is open in the subspace topo, no other singleton is open. 

#### question: is $\mathbb{Q}$ open in $\mathbb{R}$?

#### Lemma: (open in open is open)
Let $X$ be a T.S., $Y\subset X$. If $U$ is open in Y, Y is open in Xn then U is open in X. (Sufficient but not necessary condition).

#### lemma: (subspace of a subspace is a subspace)
Let X be a T.S., Y is a subspace of X, A is a subset of Y. Then the subset topo on A from Y is the same as that from X.

---
# Related Problems

---
# References
