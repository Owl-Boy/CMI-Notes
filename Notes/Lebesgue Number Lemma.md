202303012303

Type : #Note
Tags : [[Topology]]

---
# Lebesgue Number Lemma
```ad-note
title: 
Let $\mathcal{C}$ be an open cover of a compact metric space $(X,d)$. There exists a $\delta>0$ such that for each subset $B \subset X$ of diameter $< \delta$, there exists an element $U \in \mathcal{C}$ with $B \subset U$.
The number $\delta$ is called a Lebesgue number of $\mathcal{C}$.
```
##### Proof:
If $X \in \mathcal{C}$ then we are done.
Otherwise, since $X$ is compact, there is a finite subcover $U_{1},\dots,U_{n}$ of $X$. Now let $C_{i} := U_{i}^{c}$. 
Define 
$$
f(x) = \frac{1}{n} \sum\limits_{i=1}^{n} d(x,C_{i}) 
$$
Since $X$ is compact, this achieves a minimum value $\delta$, we claim this is the required _Lebesgue Number_.

Let $B$ be a set with diameter $<\delta$, then there is a point $p \in B$ such that $B \subset B_{\delta}(p)$. But then $\delta \le f(p) \le d(p,C_{m})$ for some $m \in \{ 1,2,\dots n \}$. This gives $B_{\delta}(p) \subset U_{m}$.  


---
# Related Problems

---
# References
