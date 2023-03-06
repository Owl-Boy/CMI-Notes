202303011803

Type : #Note
Tags : [[Topology]]

---
# Sequentially Compact
```ad-note
title:
A space $X$ is called _sequentially compact_ when every sequence in $X$ has a convergent subsequence.
```

### Proposition
```ad-note
title:
A first countable space is countably compact iff it is sequentially compact.
```
###### Proof:
TODO

### Theorem
```ad-note
title:
Let $X$ be a metrizable space. Then $X$ is compact iff it is sequentially compact.
```
#### Proof:
1. First show that a sequential compact space satisfies the [[Lebesgue Number Lemma]].
2. Then show that a sequentially compact space is totally bounded.
3. Now consider an open cover of a sequentially compact space, it has lebesgue number $\delta$. Let $\epsilon=\frac{\delta}{3}$. Choose a finite covering of $X$ by $\epsilon$ balls. Since each such ball has diameter less than $\delta$, there is some element of the open cover which covers this ball. This gives a finite subcover of our open cover. 

---
# Related Problems

---
# References
