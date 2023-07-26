202307250007

Type : #Note
Tags : [[Type Theory]]

---
# Product Type
A term of a product type is reducible iff its projections are
1. [[Reducibility#^CR1|CR1]] Suppose $t$ of type $U\times V$, is reducible, then $\pi^{1}t$ is reducible and by induction hypothesis for $U$, $\pi^{1}t$ is strongly normalizable. Moreover $\nu(t)\le\nu(\pi^{1}t)$ since to any reduction sequence $t,t_{1},t_{2}\dots$ we can apply $\pi_{1}$ such that the last term of the sequence corresponds to a term where $\pi_{1}$ is not reduced.
2. [[Reducibility#^CR2|CR2]] If $t\rightsquigarrow t'$ then its projections too. As $t$ is reducible by hypothesis, so are $\pi^{1}t$ and $\pi^{2}t$ and the induction hypothesis says $t'$ is also reducible.
3. [[Reducibility#^CR3|CR3]] Let $t$ be [[Reducibility#^e70af2|neutral]] and suppose all the $t'$ one step from $t$ are reducible, applying a conversion inside $\pi^{1}t$ results in $\pi^{1}t'$, since $\pi^{1}t$ cannot itself be a redex ($t$ is not a pair), and $\pi^{1}t'$ is reducible since $t'$ is. But all one step reductions of $\pi^{1}t$ are reducible, hence $\pi^{1}t$ is reducible(by induction).

---
# References
[[Arrow Type]]
[[Atomic Types]]