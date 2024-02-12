---
tags:
  - Example
---

202401161052

tags : [[Linear Programming]]

#  Optimality of Basic Feasible Solution
---
>[!Theorem]
>If the cost function is bounded withing the feasible region
>- there is an optimum 
>- and the optimum occurs at a [[Basic Feasible Solution|bfs]]

To prove the above theorem, we use the following lemma which shows that any given solution that is not a *bfs* we can find a *bfs* that is at least as good as it.
>[!theorem] Lemma
>Let $v$ be a feasible point. Then there exists a [[Basic Feasible Solution|bfs]] $u$ such that $c^Tu\ge c^Tv$

Given any point $v$ that is *feasible*. we find the set of points $S_v=\{u\;|\; u\text{ is feasible and }c^Tu\ge c^Tv\}$.
Pick a point $v^*$ such that it has the most number of non-zero coordinates.

*Claim:* $v^*$ is a [[Basic Feasible Solution|bfs]].
*Proof:* Given any vector with columns that are linearly dependent.
Then can find a $w$ such that $Aw=0$ so $A(v^*+\lambda w)=b$ and $A(v^*-\lambda w)=b$. 

>[!idea]
>Idea would be to find $\lambda$ and $w$ such that we can add it to $v^*$ without dropping its value and making one component of $v^*$ to become $0$

- $c^T w>0$
	- In this scenario, if there is a component of $w$ which is negative, then we can find a $\lambda$ such that $v^*+\lambda w$ has one extra $0$ and is better.
	- If there is not any component which is negative, then we can keep adding $w$ and increasing the cost while staying within the *feasible region*. This contradicts the assumption that the cost is bounded.
- $c^Tw<0$ - The case is symmetric to the previous one.
- $c^T w = 0$ 
	- In this case adding or subtracting $w$ does not change the cost, so if any component of $w$ has non-zero value then we can find a $\lambda$, such that we find a point that has the same cost but more $0$'s
	- We are guaranteed to find such a $w$ because we assume that the columns are linearly dependent.

---
# Related
[[Basic Feasible Solution]]
[[Solution of an LP]]