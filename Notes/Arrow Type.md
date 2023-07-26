202307250007

Type : #Note
Tags : [[Type Theory]]

---
# Arrow Type
A term of arrow type is reducible iff all its applications to reducible terms are reducible.
1. [[Reducibility#^CR1|CR1]] If $t$ is reducible of type $U\to V$, let $x$ be a variable of type $U$; the induction hypothesis([[Reducibility#^CR3|CR3]]) for $U$ says that the term $x$, which is neutral and normal, is reducible. So $t\ x$ is reducible. Just as in the case of product type, we remark that $\nu(t)\le \nu(t\ x)$. The induction hypothesis([[Reducibility#^CR1|CR1]]) for $V$ guarantees that $\nu(t\ x)$ is finite so $\nu(t)$ is finite, and the $t$ is strongly normalizable.
2. [[Reducibility#^CR2|CR2]] If $t\rightsquigarrow t'$ and $t$ is reducible, take $u$ reducible of type $U$; then $t\ u$ is reducible and $t'\ u$ is reducible hence $t'$ is reducible
3. [[Reducibility#^CR3|CR3]] Let $t$ be [[Reducibility#^e70af2|neutral]] and suppose all the $t'$ one strop from $t$ are reducible. Let $u$ be a reducible term of type $U$; we want to show that $t$ is reducible. By induction hypothesis([[Reducibility#^CR1|CR1]]) for $U$, we know that $u$ is strongly normalizable. So we can reason by induction of $\nu(u)$.
   
   In one step, $t\ u$ converts to
   - $t'\ u$ with $t'$ one step from $t$; but $t'$ is reducible, so is $t'\ u$
   - $t\ u'$ with $u'$ one step from $u$, since $u'$ is reducible, by induction hypothesis([[Reducibility#^CR2|CR2]]) for $U$, and $\nu(u')<\nu(u)$; so the induction hypothesis for $u'$ tells us that $t\ u'$ is reducible
   - since $t\ u$ cannot be a redex, it is reducible, hence $t$ is reducible

---
# References
[[Product Type]]
[[Atomic Types]]