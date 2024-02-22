---
tags:
  - Note
  - Incomplete
---
202402140902

Tags : [[Infinite State Verification]]
# A More Efficient Method for Petri Net Coverability
---
>[!info]
>After the absolutely monstrous construction of Karp-Miller tress in [[Coverability in Petri Nets is Decidable]], we ask the natural question, if its computable, is it feasible?
>Rackoff gave a much better construction with the idea "If there is a witness for coverability, then there is a small witness" and have a double exponential construction.

>[!Definition] Pseudo Markings
>For any $t\in T$, a marking is called $i$**-enabled** if $\forall j\in[1\dots i], M[i]\geq in(t, i)$.
>If we just consider these kinds of markings, say after fixing some value for $i$ then our petre-net can take transitions that makes values other than the first $i$ ones negative, but it should work normally in the first $i$ components.
>
>The notion of $i$**-enabled** also naturally gives a definition for $i$**-coverable**.

---
## Induction on *pseudo markings*
>[!idea]
>We want to show that the minimum computation it takes to get to a marking the covers the final one is well bounded, that is we want to find a good bound for 
>$$
\max\left[\min \text{ of computation from $M$ that covers $M_{f}$}\right]
>$$
We rewrite the question in the following manner

$$
f(i)=
\max\Big[\min\big[(|\sigma+1|)\;|\; \text{$M$ is a pseudo marking and $M\rightarrow M_{f}$ is an $i$-covering}\big]\Big]
$$

We will do the following by showing that 
$$
f(i+1) \leq \big(2^n f(i)\big)^{i+1}+f(i)
$$
We induct on the value of $i$
- Base Case: $f(0)=1$
- Induction Hypothesis: 
	- If each marking is bounded by $2^n\cdot f(i)$ then the maximum number of possible configurations that do not dominate the final one are $\big(2^n\cdot f(i)\big)^{i+1}$ (as we are only looking at the first $i+1$ values.). Then every run that we have has to be at most $\big(2^n\cdot f(i)\big)^{i+1}$ otherwise by PHP we will have configurations that repeat in the path so we can cut in short.
- If there are really huge markings. Then we consider a run on the petri net where $i$ is the first position where we see something of the size at least $(2^n\cdot f(i))^{i+1}$ value. Reaching this part takes at most $(2^b\cdot f(i))^{i+1} -1$ steps
		- We now ignore the one of the values that goes really high and find a $f(i)$ run on the other $i$.
		- Hence the maximum size of the fun cannot be more than $the statement we are trying to reach.


---
# References
[[Coverability in Petri Nets is Decidable]]
