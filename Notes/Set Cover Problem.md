---
tags:
  - Note
---
202309281909

Tags : [[Advanced Algorithms]]

---
# Set Cover Problem

Universe $U=\{e_{1},\dots,e_{n}\}$
Family of subsets of $U$, $\mathcal{F}=\{S_{1},\dots,S_{i}\}$, $S_{i}\subset U\ \forall i$, $\bigcup\limits_{S_{i}\in\mathcal{F}}S_{i}=U$.
Cost $c: \mathcal{F}\to Q^{+}$
**Goal:** Pick a minimum size subcollection $\mathcal{F'}\subset\mathcal{F}$ s.t. union of the collection is $U$.
- NP hardness follows because of reduction to this from vertex cover.

```ad-todo
title: Greedy Algorithm
$R:$ Set of elements covered so far
$R=\phi,\mathcal{F'}=\phi$
while $R\neq U$,
Find the most cost-effective set $S$. ($S$ has min value of $\frac{c(S)}{|S\setminus R|}=\alpha_{S}$), add to $\mathcal{F}'$. (Resolve ties arbitrarily.) $R=S\cup R$.
output $\mathcal{F'}$.
```

**Analysis:** (For a specific rum)
$S\setminus R:$ uncovered elements so far
For each element in $S\setminus R$, set $\text{price}(e)=\alpha_{S}$.

$\text{cost}(\mathcal{F'})=\sum\limits_{i=1}^{n}\text{price}(e_{i})=\sum\limits_{S\in\mathcal{F'}}c(S)$.

Arrange elements of $V$ in the order in which they are covered in the algorithm, say $e_{1},\dots,e_{n}$.
*Observe:* Before the iteration in which $e_{k}$ is covered, there are $\ge n-k+1$ uncovered elements.

```ad-note
title:Price Upper Bound 
**Claim:** 
$$
\text{price}(e_{k})\le\frac{OPT}{n-k+1}
$$

*Proof:* $\text{price}(e_{1})\le\frac{OPT}{n}$
(It is equal if the first set is U. The other sets would have at least as much mean cost as the price of $e_{1}$.)
Assume that we get the $k-1$ elements for free. This gives the bound using the same argument as above.
We can assume that because otherwise we'll have $OPT-x$ on the RHS which is only better!
```

$$
\begin{align*}
\text{cost}(\mathcal F') &= \sum\limits_{k=1}^{n}\text{price}(e_k)\\
&\le \sum\limits_{k=1}^{n}\frac{\text{cost}(OPT)}{n-k+1}\\
&= \text{cost}(OPT)\sum\limits_{i=1}^{n}\frac{1}{i}\\
&\le \text{cost}(OPT).\log(n)
\end{align*}
$$

```ad-example
title: Tightness example
Consider $\mathcal F=\{S_{i}\}.S_{1}=\{1\},S_{2}=\{2\},\dots,S_{n}=\{n\},S_{n+1}=\{1,2,\dots,n\}.$
$$
c(S_{i})= \left\{
\begin{align*}
\frac{1}{i}, && 1\le i\le n\\
1+\epsilon, && i=n+1\\
\end{align*}
\right.
$$
```

Thus the analysis is tight and we get an $H_n-$approximation.

---
# References
[[Approximation Algorithms]]
[[Vertex Cover Problem]]