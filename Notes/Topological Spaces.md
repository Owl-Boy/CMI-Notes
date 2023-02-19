202301031101

Type : #Note
Tags :[[Topology]]

---
# Topological Spaces
Let $X$ be a set.
A **Topology** on $X$ isa  collection $\tau$ of subsets of $X$ such that they follow the following properties
1. $\emptyset, X$ are both in $\tau$
2. (Arbitrary unions)
   $\{U_\alpha\}_{\alpha\in\tau}$ such that each $U_\alpha\in\tau$ then $\bigcup\limits_{\alpha\in\tau}\in\tau$ 
3. (Finite intrersection)
   $\{U_1,U_2\dots U_n\}\in\tau\implies\bigcap\limits_{i=1}^nU_i\in\tau$
Members of $\tau$ are defined as **open sets**
##### Example
- This is the _Standard topology_ on $\mathbb R^n$
$$
\begin{aligned}
x&\in\mathbb R^n\\
B_\varepsilon(x)&=\{y\in\mathbb R^n|d(x,y)<\varepsilon\}\\
\tau_{\mathbb R^n}&=\{U\subseteq X|\forall x\in U,\exists \text{ such that } B_\varepsilon(x)\subseteq U\}
\end{aligned}
$$

Usually a topology can be specified with a, smaller subcollection.
- The topolgy created by all subsets of a set is called the discrete topology
- let $X$ bet a set, the topology $\tau_X=\{\emptyset,X\}$ is called the trivial topology
- let $X=\{a,b\}$, for this set, some of the possible topologies would be
	- Trival Topology
	- Discrete Topology
	- $\tau_a=\{\emptyset,\{a\}, X\}$
	- $\tau_b=\{\emptyset,\{b\}, X\}$
	In case of $\tau_a$, the element $a$ is _separated away_ from the other point $b$ as there is an open set which contains $a$ but no open set that contains $b$, which means $a$ can get arbitrarily close to $b$ but $b$ cannot get arbitrarily close to $a$ .
	There does not exists a metric on this topology
- let $X$ be a set. let $\tau_X$ = collection of sets $U\subset X$ such that $U\setminus X$ is finite or $X$
	- $\emptyset\in\tau_X, X\in\tau_X$
	- $\{U_\alpha\}$ if each $U_\alpha$ is empty $\implies$ $\bigcup U_\alpha\in \tau_X$, otherwise $U_\beta$ is no empty for some $\beta$ and $X\setminus U_\beta$ is finite, 
	  if $V=\bigcup\limits_{\alpha\in\tau}X_\alpha, X\setminus V\subset X\setminus U_\beta$
	- $\{U_1,U_2\dots U_n\}$ if some $U$ is empty, $W$ is empty where $W=\bigcap\limits_{i=1}^n U_\alpha$, if none of $U$ are empty then $X\setminus W=(X\setminus U_1)\cup(X\setminus U_2)\cup\dots\cup(X\setminus U_n)$
- $X=\mathbb R$ and $\tau_X=\{(a, \infty) | a\in\mathbb R\}$, This is called _Ray Topology_.
- [[Subspace Topology]]
- [[Product topology]]
- [[Order Topology]]

For some $X$ , $\tau_X,\tau'_X$ are two topologies on $X$ and if $\tau\subset \tau'$ then $\tau$ is said to be **coarser** than $\tau'$.
 
---
# Related Problems

---
# References
[[What is Topology]]