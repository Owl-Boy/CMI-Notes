202307250007 ^0b2b53

Type : #Note
Tags : [[Type Theory]]

---
# Reducibility Theorems
### Pairing
If $u$ and $v$ are reducible, so is $\langle u, v\rangle$.

Because of [[Reducibility#^cf45af|CR 1]], we can reason by induction of $\nu(u)+\nu(v)$ to show that $\pi^{1}\langle u,v\rangle$ is reducible. This term converts to:
- $u$, which is reducible.
- $\pi_{1}\langle u', v\rangle$, with $u'$ one step from $u$. $u'$ is reducible by [[Reducibility#^7b3975|CR 2]], and we have $\nu(u)<\nu(u')$; so the induction hypothesis tells us this term is reducible
- same with $\pi^{1}\langle u, v'\rangle$
This shows $\pi_{1}\langle u,v \rangle$ is reducible, same argument works for $\pi^{2}\langle u, v \rangle$

### Abstraction
If for all reducible $u$ of type $U$, $v[u/x]$ is reducible then so is $\lambda x.v$. We again reason on $\nu(u)+\nu(v)$

The term $(\lambda x.v)u$ converts to
- $v[u/x]$ is reducible by hypothesis
- $(\lambda x.v') u$ with $v'$ being one step away from $v$. So $v'$ is reducible, $\nu(v')<\nu(v)$, and then induction tells us this term is reducible
- $(\lambda x.v) u'$ with $u'$ being one step away from $u$. So $u'$ is reducible, $\nu(v')<\nu(v)$, and then induction tells us this term is reducible
In every case the neutral term $(\lambda x.v)u$ converts to reducible terms only, and by [[Reducibility#^5083eb|CR 3]] it is reducible. so $\lambda x.v$ is reducible

---
# References
[[Reducibility]]
[[Strong Normalization Theorem]]