202308161608

Type : #Note
Tags : [[Logic]]

---
# Heyting Algebra
```ad-note
title:definition

A distributive [[Lattice|lattice]] with $0$ and $1$ such that for all $a, b\in H$ we have $a\implies b\in H$
```

^definition

Every element $c$ in a _Heyting Algebra_ is called a _Relative Pseudo-Complement_ of $a$ with respect to $b$ iff $c$ is the greatest element such that $a\sqcap c\le b$ and is denoted by $a\implies b$. The special case of $a\Rightarrow 0$ can also be written as $-a$ .

A _valuatation_ in a **Heyting Algebra** is a map $\nu:\text{PV}\to H$ given by
![[Pasted image 20230910155621.png|400]]
and we have the following notion:
![[Pasted image 20230910155706.png|450]]

## Pierce's Law and Law of Excluded 
Both of the above two laws, are not valid in **Heyting Algebras**. Which can be proven by the following constructions.

Let
$$
\mathcal H = \langle O(\mathcal T),\cup,\cap,\Rightarrow,\sim,\emptyset,\mathcal T\rangle
$$
where $\mathcal T$ is a [[Topological Spaces| Topological space]]. let $\mathcal T=\mathbb R$ 

*Pierce's law* is
$$
((p\to q) \to p)\to p
$$
Consider $\nu(p)=\mathbb R\setminus\{0\}$ and $\nu(q)=\emptyset$. Then we get 
$$
\begin{align*}
\textlbrackdbl p\to q\textrbrackdbl &= \text{Int}(\{0\}\cup\emptyset)=\emptyset\\
\textlbrackdbl (p\to q)\to p\textrbrackdbl &= \text{Int}(\mathbb R\cup \mathbb R\setminus\{0\})=\mathbb R\\
\textlbrackdbl ((p\to q)\to p)\to p \textrbrackdbl &= \text{Int}(\emptyset\cup\mathbb R\setminus\{0\})=\mathbb R\setminus\{0\}\ne\mathbb R\\
\end{align*}
$$
For the _law of excluded_ middle 
take $\nu(p)=(0,\infty)$ 
Then we get $\nu(-p)=(-\infty,0)$
and $\nu(p\lor-p)=\mathbb R\setminus \{0\}$

## Example:
$(\theta(\mathbb R),\cup,\cap,\implies,\emptyset,\mathbb R)$
where $A\implies B=\text{Int}(-A\cup B)$
$\sim A=\text{Int}(-A)$

---
# References
[[Lattice]]
[[Kripke Models]]