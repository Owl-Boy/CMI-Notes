202303241403

Type : #Note
Tags : [[Topology]]

---
# Urysohn Metrization Theorem
```ad-note
title:
Every regular second countable space is metrizable.
```

##### Proof:
We prove two claims and the result follows from them.
###### Claim 1:
There is a countable collection $\{ f_{n} \}_{n \in \mathbb{N}}$ of maps $f_{n} : X \to [0,1]$, such that for any $p \in U \subseteq X$ with $U$ open, there is an $f_{n}$ in the collection such that $f_{n}(p) = 1$ and $f_{n}(X\setminus U)= \{ 0 \}$.

###### Claim 2:
The function $F : X \to [0,1]^{\omega}$ given by $F(x) = (f_{1}(x),f_{2}(x),\dots)$ is an embedding.

It is easy to see the result follows from this, since subspace of a metrizable space is metrizable.

###### Proof of Claim 1:
For each pair $(i,j)$ of indices with $Cl(B_{i}) \subseteq B_{j}$, use Urysohn's lemma to get a function $g_{i,j}$ which is 1 on $B_{i}$ and 0 on $X\setminus B_{j}$.
Now for any $p \in U$ with $U$ open, pick a basis element $B_{i}$ s.t. $p \in B_{i} \subseteq U$, then by regularity, there is an open set $V$ such that $p \in V \subseteq Cl(V) \subseteq B_{i} \subseteq U$.
Then there is a $B_{j}$ s.t. $p \in B_{j} \subseteq V$.
So take $g_{j,i}$ as the required function.
Now just reindex the g's to get the f's.

###### Proof of Claim 2:
$F$ is cts since each of the components is cts.
$F$ is also injective. Let $F(x) = F(y)$ then $f_{i}(x) = f_{i}(y)$ for all $i$. But, since $x,y$ are closed as singletons, and $X$ is regular, there are open nbhds $U,V$ of $x,y$ respectively which are disjoint. But this means that $f_{n}(x) = 1$ and $f_{n}(y) = 0$ for some $n$.

We need to show that given $U \subset X$ open, $F(U) \subset F(X)$ is open.
Let $x_{0} \in U$ be any element. There exists $f_{n}$ such that $f_{n}(x_{0}) = 1$ and $f_{n}(X\setminus U) \subset \{ 0 \}$.
Let $V_{n} := \pi_{n} ^{-1}((0,1]) \cap F(X)$, here $\pi_{n}$ is the nth projection map from $[0,1]^{\omega}$.
So, $V_{n}$ is open in $F(X)$, $x_{0} \in F ^{-1}(V_{n}) \subset U$. Hence $F(x_{0}) \in V_{n} \subseteq F(U)$, giving $F(U)$ open.

#### NOTE: The construction used can be used to show that if normal space $X$ has a basis indexed by $J$ then we can embed $X$ into $\mathbb{R}^{J}$
---
# References

[[Urysohn Lemma]]
[[Regular Spaces]]
[[Second Countability]]
[[Product topology]]
[[Metrizable Spaces]]
[[Subspace Topology]]
[[Continuous Functions]]
[[Homeomorphisms]]