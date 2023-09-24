202308202308

Type : #Note
Tags : [[Algebraic Graph Theory]]

---
# Asymmetric Graphs
A graph is called _asymmetric_ if its automorphism group is the identity group.

## Theorem
Almost all graphs are Asymmetrical

## Proof
Given $n$ vertices on a graph. The number of possible edges is $n\choose 2$, hence the total number of possible graphs with $n$ vertices are $2^{n\choose 2}$. 

Given a graph $X$, the set of isomorphic graphs to $X$ is called the isomorphism class of $X$. And the size of the isomorphism class of $X$ is 
$$
\frac{n!}{|\text{Aut}(X)|}
$$
Proof from [Orbit Stabilizer Theorem](https://proofwiki.org/wiki/Orbit-Stabilizer_Theorem) .

If a permutation of vertices has $r$ orbits, then it fixes at least $2^{r}$ sets of edges(r sets directly and union of those sets of edges). Then [[Burnside's Lemma]] states that the number of isomorphism classes on a vertex set $V$ is equal to 
$$
\frac{1}{n!}\sum\limits_{g\in\text{Sym}(V)}2^{orb_{2}(g)}
$$And if all graphs were asymmetrical then every isomorphism class would contain $n!$ elments and the number of isomorphism class would be 
$$
\frac{2^{n\choose 2}}{n!}
$$
We use the following lemma
![[Lemma-Number of isomorphism classes on graphs#^8f4dba]]

Suppose the proportion of isomorphic classes that are asymmetric is $\mu$ and each isomorphic class that is not asymmetric contains atmost $\frac{n!}{2}$ elements. Then the average size of an isomorphism class is atmost 
$$
n!\left(\mu + \frac{1-\mu}{2}\right)=\frac{n!}{2}(1+\mu)
$$
Hence 
$$
\frac{n!}{2}(1+\mu)(1+o(1)) \frac{2^{n\choose 2}}{n!}>2
$$
which implies $\mu = 1$.
Since the proportion of Asymmetric graphs is atleast as much as the proportion of ismorphic classes as they have the largest ismorphism groups, it follows that almost all graphs as asymmetric.

---
# References
[[Lemma-Number of isomorphism classes on graphs]]