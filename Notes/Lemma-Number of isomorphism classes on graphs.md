202308210142

type : #Example
tags : [[Algebraic Graph Theory]]

#  Lemma-Number of isomorphism classes on graphs
---
### Lemma:

**Lemma:** The actual number of isomorphism classes on graphs are 
$$(1+o(1))\frac{2^{n\choose 2}}{n!}$$ ^8f4dba
###  Proof:

Let _Support_ be the set of points that are not fixed by a permutation. If the support is the  even number $2r$ then the maximum number of orbits are given by $r$ cycles of length $2$. Looking at the effect of these permutations on edges. there are $2$ ways an edge can not be fixed by the permutation. First is if both the edges of the edge are in the support and the second is if exactly of the ends are in the support.
Given that there are $2r$ vertices that in the support, the number of edges that are not fixed are 
$$
r(n-r-1)
$$
Hence the total number of orbits of a permutation $g$ on the edges are
$$
\text{orb}_2(g)={n\choose 2}-r(n-r-1)
$$
Now we fix $m\le n-2$ and partition the permutation of vertices into $3$ categories.
The first one being identity, the second one being where the number of fixed points $\le m$
We can estimate the size of the partitions as follows 
$$
\begin{align*}
|\mathcal C_{1}|&= 1 \\
|\mathcal C_{2}|&\le {n\choose m}m!\le n^{m} \\
|\mathcal C_{3}|&\le n! \le n^{m}\\
\end{align*}
$$
A permutation belonging to $\mathcal C_{2}$ has at most ${n\choose 2}-{n-m \choose 2}$ such orbits
A permutation belonging to $\mathcal C_{3}$ as atleast $m$ points in the support, so it has maximum number of orbits if it has $\frac{m}{2}$ cycles in which case it has less than 
![[Pasted image 20230821013227.png|300]]
many orbits
Hence 
![[Pasted image 20230821013359.png]]
Where the sum of last to terms is $o(1)$ 

---
# Related


