202307242307

Type : #Note
Tags : [[Type Theory]]

---
# Strong Normalization Theorem
### Theorem:
All terms are [[Reducibility|reducible]]

Hence all terms are _Strongly Normalizable_.

In the proof of the theorem, we need a stronger induction hypothesis to handle the case of abstraction. This is the purpose of the following proposition, from which the theorem follows by butting $u_{i}=x_{i}$

### Proposition
Let $t$ be any term, and suppose all the free variables of $t$ are among $x_{1}, x_{2}\dots x_{n}$ of the types $U_{1}, U_{2}\dots U_{n}$. if $u_{1}, u_{2}\dots u_{n}$ are reducible terms of the above types then $t[u_{1}/x_{1}, u_{2}/x_{2}, \dots u_{n}/x_{n}]$ is reducible

### Proof
By induction of $t$. We write $t[u/x]$ for the above term
1. $t$ is $x_{i}$ : Trivial
2. $t$ is $\pi^{1}w$: by induction hypothesis, for every sequence $\underline u$ of reducible terms, $w[u/x]$ is reducible. That means that $\pi^{1}[u/x]$ is reducible, but this term is nothing other than $\pi^{1}w[u/x]=t[u/x]$
3. $t$ is $\pi^{2}w$: Same as the above point
4. $t$ is $\langle v, w \rangle$: by induction hypothesis both $v[u/x]$ and $w[u/x]$ are reducible.
   [[Reducibility Theorems#Pairing]] says that $t[u/x]=\langle v[u/x],w[u/x]\rangle$ is reducible.
5. $t$ is $w\ v$: by induction hypothesis $w[u/x]$ and $w[v/x]$ are reducible, anbd so by definition $w[u/x](v[u/x])$ is reducible which is just $t[u/x]$
6. $t$ is $\lambda y.w$ of type $V\to W$: by induction hypothesis, $w[u/x,v]$ is reducible for all $v$ of type $V$. [[Reducibility Theorems#Abstraction]] says that $t[u/x]=\lambda y.(w[u/x])$ is reducible

Hence, the proposition and the preceding theorem is also true.

---
# References
[[Reducibility]]