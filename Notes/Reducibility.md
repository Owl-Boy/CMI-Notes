202307242307 ^4ec029

Type : #Note
Tags : [[Type Theory]], [[Lambda Calculus]]

---
# Reducibility

## Definition
We define a set $RED_{T}$ ("_Reducible_ term of type $T$") by induction on the type $T$

1. for $t$ of atomic type $T$, $t$ is reducible if it is strongly normalisable. ^cf45af
2. for $t$ of type $U\times V$, $t$ is reducible if its two projections are reducible ^7b3975
3. for $t$ of type $U\to V$, $t$ is reducible if for all reducible $u$ of type $U$, $t\ u$ is reducible of type $V$ ^5083eb


The reason why redicibility works where combinatorial intuition fails is because of the complexity

$t\in RED_{U\to V}\iff\forall u(u\in RED_{U}\implies t\ u\in RED_{V})$

## Properties
```ad-note
title:Neutrality
A term is called _neutral_ if it is not of the form $\langle u,v\rangle$ or $\lambda x.v$. In other words, neutral terms are those which are of the form
- $x$
- $\pi^{1}t$
- $\pi^{2}t$
- $t\ u$
```

^e70af2

The conditions that interest are 
- **CR1:** If $t\in RED_{T}$ then $t$ is strongly normalizable ^CR1
- **CR2:** If $t\in RED_{T}$ and $t\rightsquigarrow t'$ then $t'\in RED_{T}$ ^CR2
- **CR3:** If $t$ is neutral, and whenever we convert a redex of $t$ we obtain a term $t'\in RED_{T}$ then $t\in RED_{T}$ ^CR3
- **CR4:** If $t$ is neutral and normal then $t\in RED_{T}$  ^CR4

---
# References
[[Atomic Types]]
[[Product Type]]
[[Atomic Types]]
[[Reducibility Theorems]]