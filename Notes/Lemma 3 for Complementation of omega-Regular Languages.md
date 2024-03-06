---
tags:
  - Example
---

202401122347

tags : [[Automata Theory]]

#  If $L_1$ and $L_2$ are equivalence classes, then $L_1(L_2)^\omega$ is either a subset of $L_A$ or disjoint from it.
---
If $L_1(L_2)^\omega\cap L_{A}$ is empty then the case is trivial.
Otherwise say $w$ is in the intersection.

Let $r$ be an accepting run of $w$. Then we need to show that for all $w'\in L_{1}(L_{2})^\omega$ we need to find a run $r'$ on it which is accepting.

Let $w= w_{1}(w_{2,1}w_{2,2}\dots)$ where $w_1$ is in $L_1$ and each $w_{2,i}$ is in $L_2$.

We now show that for any given $w'$, there exits such an $r'$.
We build $r'$ inductively in the following way.
We break $w'$ the same as $w$ into $w'_1(w'_{2,1}w'_{2,2}\dots)$. Now by the definition of $\sim_A$we can say if $w_\alpha$ has a run that traces a path from $p$ to $q$, so does $w'_\alpha$.  And if the path goes over a good state for $w_\alpha$ it will also do so for $w'_\alpha$.

Hence we break the $r$ into many tiny runs for each $w_{\alpha}$ and have the starting and end points of each of those subruns be the same for subruns for $w'_\alpha$.

We call a subrun good, if it passes over a good state.  
We also make sure all good subruns of $w$ correspond to good subruns of $w'$.

hence $w'\in L_A$.

---
# Related
[[Lemma 1 for Complementation of omega-Regular Languages]]
[[Lemma 2 for Complementation of omega-Regular Languages]]