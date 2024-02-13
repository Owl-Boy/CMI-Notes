---
tags:
  - Example
---

202402111607

tags : [[Infinite State Verification]]

#  Properties of Karp-Miller Trees
---

>[!theorem]
If $\sigma:M_{0}\rightsquigarrow M$ is a run in the petri net $\mathcal P$, then there exists a run $\sigma' :M_{0}\rightsquigarrow M'$ in the carp miller tree of $\mathcal P$ such that $M'\ge M$.

***Proof:*** Induction of the size of the run:
- Base case (length $0$): There is a node corresponding to the marking $M_0$ hence this is trivial.
- Induction step: 
	- Consider the run $\lambda : M_{0}\rightsquigarrow N$ such that $N$ goes to $M$ using transition $T$ and the corresponding run $\lambda' : M_{0}\rightsquigarrow N'$ such that $N' \geq N$.
	- At the node $N'$ the transition corresponding to $T$ is enabled. Hence we take it to get to the node $M'$.

---

>[!theorem]
>If there is a run $\sigma^\omega : M_{0}^\omega\rightsquigarrow M^\omega$ on the graph of petri net $\mathcal P$, then there exists a run $\sigma:M_{0}\rightsquigarrow M$ such that 
>- $M(i) = M^\omega(i)$ if $M^\omega(i)\neq\omega$ .
>- given an $n$ we can gave $M(i) \ge n$ if $M^\omega(i)=\omega$

***Proof:*** Induction of the size of the run:
- Base case (length $0$): just the start configuration. trivial
- Induction Hypothesis: The theorem is true for the prefix of the run upto the last time(call it $N^\omega$) an $\omega$ was introduced in the configurations in the run before $M^\omega$ 
- Induction step:
	- If $M^\omega$ does not contain any $\omega$ elements, then just take the sequence of transitions that correspond to $\sigma$ in $\mathcal P$.
	- If $M^\omega$ does contain $\omega$ elements then for any $M'$ in the run $M'(i) = \omega \implies M^\omega(i)=\omega$.  
		- If $\omega$ was not introduced in $M^\omega$. Consider the the run up to $N^\omega$, If the part of the run from $N^\omega$ to $M^\omega$ removes at most $k$ in total, from an $\omega$ element. find the run to $N$ in the petri net where each element corresponding to $\omega$ in $N^\omega$ has value atleast $n+k$. Then take the sequence of transitions that correspond to run from $N^\omega$ to $M^\omega$.
		- If $\omega$ was introduced in $M^\omega$, then by construction we have a marking $M_{1}^\omega$ which is in the run and $M_{1}^\omega(i)=M^\omega(i)$ if  $M^\omega(i)\ne \omega$ and $M_1^\omega\le M^\omega$. Using IH and the above point, theorem is valid for sub-run up to $M_1^\omega$. Consider the sub-run from $M_1^\omega$ to $M^\omega$. If it removes at most $k$ in total from an $\omega$ element. Then we find a run from $M_0$ to $M_1$ where elements corresponding to $\omega$ elements have value $n\cdot(k+1)$. Then we repeat the subrun from $M_1^\omega$ to $M^\omega$ $n$ times.


---
# Related
[[Coverability in Petri Nets is Decidable]]