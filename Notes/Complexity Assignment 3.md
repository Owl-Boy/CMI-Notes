---
tags:
  - Assignment
---

# Assignment 3
---
Name: Aditi Muthkhod
Roll Number: BMC202107

## 1.
### (a)
---
Observe that there are at most $2^{n^{c}}$ different possible circuits $C_{n}$ of size $n^{c}$.
However, there are $2^{p(n)}$ possible subsets $S$ of $L_{p(n),n}$.
If we pick $p(n)=\Theta(n^{c+1})$ (this, of course, exists), then we get that there exists a constant $n_{0}$ such that $p(n)>n^{c}$ for all $n>n_{0}$. So, $2^{p(n)}>2^{n^{c}}$, for $n>n_{0}$. Thus by pigeonhole principle, there is some language $S_{n}\subseteq L_{p(n),n}$ that is not recognised by any of the $C_{n}$ (since each circuit recognises at most one distinct language).

### (b)
---
It suffices to show that for any $S_{n}\subseteq L_{p(n),n}$, $S_{n}\in\Sigma_{3}^{P}$.
We can see that:
$x \in S_{n}\implies \exists y=p(|x|),\ y\in\{ 0,1 \}^{q(|x|)},\ \exists z=S\quad R(x,y,z)$, where $R(x,y,z)=(x<p(|x|))\land(x \in S)$.
no
aaaaaaa


### (c)
---
Assume FTSOC that $\Sigma_{2}^{P}= NP^{NP} \subseteq SIZE(n^{c})$.
This implies $NP \subseteq SIZE(n^{c})$, or in other words, that $SAT$ has polynomial size circuits. From Karp-Lipton theorem, it follows that $PH=\Sigma_{2}^{P}=\Sigma_{3}^{P}\subseteq SIZE(n^{c})$. But that is a contradiction to (b)!

## 2.
### (a)
---
 We want to show that for any $L$, $L \in S\implies L\in\Sigma_{2}^{P}$.
 Let $L\in S$.
 For any $x \in\Sigma^{*}$,
$$
x \in L\implies \exists y\in\{ 0,1 \}^{p(|x|)}\ \forall z\in\{ 0,1 \}^{p(|x|)} R(x,y,z), \text{ and}
$$$$
\begin{align}
x\not\in L&\implies \exists z\in\{ 0,1 \}^{p(|x|)}\ \forall y \in\{ 0,1 \}^{p(|x|)}\ \lnot R(x,y,z) \\
&\implies \forall y\in\{ 0,1 \}^{p(|x|)}\ \exists z\in\{ 0,1 \}^{p(|x|)}\ \lnot R(x,y,z)&&\text{(weakening)} \\
&\implies \lnot(\exists y\in\{ 0,1 \}^{p(|x|)}\ \forall z\in\{ 0,1 \}^{p(|x|)}\ R(x,y,z)).
\end{align}
$$
Thus $x \in L \iff \exists y\in\{ 0,1 \}^{p(|x|)}\ \forall z\in\{ 0,1 \}^{p(|x|)} R(x,y,z)$, which implies $L \in\Sigma_{2}^{P}$.


### (b)
---
For any language in $P^{NP}$, we have a corresponding deterministic polytime machine $M$, that makes polynomially many queries to the $NP$ oracle (i.e. the $SAT$ oracle).

So, if $x \in L$, $M$ has an accepting path. That is, there exist queries $Q_{1},\dots,Q_{k}$ (made to the $NP$ oracle), and answers $(a_{1},\dots,a_{k})$, $a_{i}\in\{ 0,1 \}$, such that
if $a_{i}=1$, then $\exists y_{i}\in\{ 0,1 \}^{p(|x|)}\ (Q_{i}(y_{i})=1)$, and
if $a_{j}=0$, then $\forall z_{j}\in\{ 0,1 \}^{p(|x|)}\ (Q_{j}(z_{j})=0)$,
and $M$ makes the query $Q_{l}$, and gets the answer $a_{l}$, and then $Q_{l+1}$, to get $a_{l+1}$, and so on, and finally accepts.
In lesser words, $\exists (\bar{Q},\bar{a},\bar{y}),\ \forall \bar{z}\quad R(x,(\bar{Q},\bar{a},\bar{y}),\bar{z})$, where $R$ is a function that verifies that the $Q_{i}$'s are correct, in order, and the $a_{i}$'s are also correct, using $y_{i}$'s and $z_{i}$'s.

> [!note] $M$ has only one path here (deterministic), and it accepts on that path. But we are saying that $M$ *has* an accepting path, because that is weaker, but sufficient for our purposes.

Similarly if $x \not\in L$, $M$ rejects. Let's say it makes queries $Q'_{1},\dots,Q'_{k'}$ (to the $NP$ oracle), and gets answers $(a'_{1},\dots,a'_{k'})$, $a'_{i}\in\{ 0,1 \}$.
We would like to say that $\exists \bar{z}, \forall(\bar{Q'},\bar{a'},\bar{y})\quad \lnot R(x,(\bar{Q'},\bar{a'},\bar{y}),\bar{z})$.

We claim that the following $\bar{z}$ works:
- If $Q'_{i}$ is satisfiable, $\exists t_{i}\in\{ 0,1 \}^{p(|x|)}\ (Q'_{i}(t_{i})=1)$, set $z_{i}=t_{i}$.
- If $Q'_{j}$ is unsatisfiable, set $z_{j}$ to be anything in $\{ 0,1 \}^{p(|x|)}$, $Q'_{j}(z_{j})$ will be $0$.
*Proof:* FTSOC $\exists(\bar{Q'},\bar{a'},\bar{y})$ s.t. $R(x,(\bar{Q'},\bar{a'},\bar{y}),\bar{z})\equiv True$. (overwriting notation)
Since $R$ has verified this, $Q'_{1}$ is correct.
If $a'_{1}=1$, since $R$ has verified, $Q'_{1}(y_{1})=1$. Thus $y_{1}$ is proof that $a'_{1}$ is the correct answer to $Q'_{1}$.
If $a'_{1}=0$, but $Q'_{1}$ is satisfiable, then $Q'_{1}(z_{1})=1$, which means this is inconsistent and $R$ will be $False$, which is a contradiction. Thus, $a'_{1}$ is the correct answer to $Q'_{1}$ in this case as well.
Now, since $Q'_{1}$ and $a'_{1}$ are correct, $Q'_{2}$ has to be correct, since $R$ has verified this. Inductively, we get that all the $Q'_{i}$'s and $a'_{i}$'s are correct, and exactly the queries and answers that $M$ makes and gets, respectively. So if $x \not\in L$, $M$ would have rejected $x$, i.e. $R(x,(\bar{Q'},\bar{a'},\bar{y}),\bar{z})\equiv False$, which is a contradiction.

Thus $L\in P^{NP}\implies L\in S$.

### (c)
---
From Karp-Lipton theorem we know that if $SAT$ has polynomial size circuits, then the polynomial hierarchy collapses to $\Sigma_{2}^{P}=NP^{NP}$. Assuming $SAT$ has polynomial circuits, if we show that $NP^{NP}=P^{NP}$, then (a) and (b) would imply (c)...


## 3.
### (a)
---
In $\det(X')$, each non zero term would correspond to a set of $n$ edges, $(i,\sigma(i)),\ \forall i\in[n]$. In this induced subgraph, all the vertices have degree $2$, so the subgraph is just a collection of cycles.

If there is an odd cycle of length $2k+1$, then the term corresponding to this subgraph would be $t=sgn(\sigma)x_{i_{1},i_{2}}\dots x_{i_{2k}i_{2k+1}}x_{i_{2k+1}i_{1}}q(\bar{x})$, where $\sigma(i_{j})=i_{j+1}$, indices taken mod $2k+1$. Consider the permutation $\sigma'$, s.t. $\sigma'(i_{j})=i_{j-1}$, indices taken mod $2k+1$, and $\sigma'=\sigma$ on the vertices not in the cycle. $sgn(\sigma)=sgn(\sigma')$ (because their difference gives two permutations that are inverses of each other). So the set of edges corresponding to $\sigma'$ contributes the term $(-1)^{2k+1}t=-t$. So these two terms cancel each other. Thus the terms corresponding to subgraphs with odd cycles will not survive.

With all even cycles, these terms don't cancel, because all the different terms corresponding to a subgraph have the same sign. Thus we get a perfect matching iff $\det(X')\neq 0$.

### (b)
---
Plug in a random value (...) to check if $\det(X')$ is non zero.
Now, remove an edge (with endpoints), and check in the subgraph, induct.

Let $p(\bar{x})=\det(X')$
As done in class for the determinant of the Lovasz matrix, we can take a set $S$ of integers. Let $d$ equal the degree of the determinant of the Tutte matrix.
Then, if the determinant is non-zero, the Schwarz-Zippel lemma tells us that $Pr[p(\bar{a})\neq 0]\geq 1-\frac{d}{|S|}$, where $\bar{a}=(a_{1,1},a_{1,2},\dots,a_{1,n},a_{2,2},\dots,a_{2,n},\dots,a_{n,n})$, and $a_{i,j}\in S,\ i<j$.

Let $p$ be the probability that on a random point $\bar{a}$, the determinant evaluates to zero, despite being a non zero polynomial. We have established $p\leq \frac{d}{|S|}$.
Given $G$ has a perfect matching, we perform the following algorithm:

```
REMOVE-EXTRA-EDGES(G):
If |E(G)|=|V(G)|/2, return E(G).
M=[]
Otherwise:
	For each e in E:
		Check if det of the Tutte matrix of G\e is non zero by querying a random point in S'.
		If it is zero, set M = M+e, continue.
		Otherwise, remove e from G, set G = G\e, continue.
	return M.
```

This algorithm makes an error in the following way: In the $i^{th}$ iteration, an extra edge was not removed because the determinant evaluated to zero, although it is not identically zero.  So $M$ will have that extra edge. This happens with probability $p$. Going over all non matching (wrt the specific matching we end up with) edges, this happens with probability at most $p\left( |E|-\frac{|V|}{2} \right)\leq \frac{d}{|S|}\left( m- \frac{n}{2} \right)$.
We can make this probability low by choosing $S$ large enough.