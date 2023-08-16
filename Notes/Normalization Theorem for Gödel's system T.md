202307261607

Type : #Note
Tags : [[Type Theory]]

---
# Normalization Theorem for Gödel's system T
In $\text{T}$ , all the reduction sequences are finite and lead to the same normal form.

## Proof
Part of the result in the extension of Church-Rosser; The other part is a strong normalization result, for which [[Reducibility]] is well adept(was actually created for $\text T$)

First we extend the notion of [[Reducibility#^e70af2|Neutrality]]: A term is normal if it is not of the from $\langle u, v\rangle,\ \lambda x.v,\ \text O, \text S\ t, \text T,\text F$. Then without changing anythign we show successively:
1. $\text O,\ \text T$ and $\text F$ are reducible - They are normal terms of atomic type.
2. If $t$ of type $\text{Int}$ is reducible (i.e. it is strongly normalizable), then $\text S\ t$ is also reducible which comes from $\nu(\text S\ t)=\nu(t)$.
3. If $u,\ v,\ t$ are reducible, then $\text D\ u\ v\ t$ is reducible - $u,v,t$ are strongly normalizable by [[Reducibility#^CR1|CR1]], and so one can reason by induction on the number $\nu(u)+\nu(v)+\nu(t)$. The neutral term $\text D\ u\ v\ t$ converts to one of the following terms
	1. $\text D\ u'\ v'\ t'$. In this case we have $\nu(u')+\nu(v')+\nu(t')<\nu(u)+\nu(v)+\nu(t)$, and by induction the terms are reducible.
	2. $u$ or $v$ if $t$ is $\text T$ or $\text F$; These two terms are reducible
	3. so we conclude by [[Reducibility#^CR3|CR3]] that the term is reducible
4. If $u,v,t$ are reducible, then $\text R\ u\ v\ t$ is reducible. Here we reason by induction but on $\nu(u)+\nu(v)+\nu(t)+l(t)$, where $l(t)$ is the number of symbols of the normal form of $t$. in one step $\text R\ u\ v\ t$ converts to
	1. $\text R\ u'\ v'\ t'$ which is reducible by induction.
	2. $u$ if $t=O$ which is reducible
	3. $v\ (\text R\ u\ v\ w) w$, where $\text S\ w=t$; since $\nu(w)=\nu(t)$ and $l(w)<l(t)$, the induction hypothesis tells us that $\text R\ u\ v\ w$ is reducible. As $v$ and $w$ are reducible, so is the term.

System $\text T$'s expressive power is discussed [[Expressive Power of Gödel's system T|here]].

---
# References
[[Strong Normalization Theorem]]