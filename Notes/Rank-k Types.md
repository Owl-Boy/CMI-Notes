---
tags:
  - Note
  - Incomplete
---
202311292311

Tags : [[Logic]]
# Rank-k Types
---
>[!info] Intuition/Theorem
>In a relational vocabulary.
>
> If we are allowed to use precisely $m$ variables, and we have no function symbols, then the number of atomic formulas are finite.
> $\text{FO}[0]$ is precisely the boolean formulas of finite variables. Hence $\text{FO}[0]$ is also finite, up to logical equivalence.
>$\text{FO}[k]$ with $m$ variables is just the boolean combinations of $\text{FO}[k-1]$ with $m$ variables and $\exists x \varphi$ where $\varphi\in \text{FO}[k-1]$ with $m+1$ variables. 
>This shows that $\text{FO}[k]$ with $m$ variables is a finite set of formulas up to equivalence for all $k$ and $m$

That was a rather concrete motivation. This is because once we give a structure and assign values to the variables, we would finally be able to make sense of it as giving extra constants  to the language and replacing all the variables with it.

---
>[!note] Definition
>A rank-$k$ $m$-type of a tuple $\vec{a}$ of size $m$ over the structure $\mathfrak A$  is the set of all $k$-rank formulae with $m$ variable that are satisfied by $\vec{a}$.
>$$
>\text{tp}_{k}(\mathfrak A,\vec{a})=\{\;\varphi\in \text{FO}[k]\quad|\quad\mathfrak A\models\varphi(\vec{a})\;\}
>$$

From the Intuition/Theorem above, we get that there are only finitely many rank-$k$ $m$-types. Since we have finitely  many formulas upto equivalence, a type can be identified with the maximal subset of $\text{FO}[k]$ formulas that it satisfies. so each type has a representative element which is:
$$
\alpha_{K}(\vec{x})=\bigwedge_{i\in K}\varphi_{i}\land\bigwedge_{j\not\in K}\lnot\varphi
$$
where $K$ represents the indices of elemets in a subset of $\text{FO}[k]$.

---
>[!note] Theorem
>1. For any finite relational vocabulary, the number of differnt rank-$k$ $m$-types is finite.
>2. For all types, we have representative formulae $\alpha_1(\vec{x})\dots\alpha_r(\vec{x})$ 
>	1. For all $\mathfrak A$ and $\vec a$ we have a representative formula which would be one of the above.
>	2. Every formula is a equivalent to a disjunction of $\alpha_i$'s

Part 2.2 lets us prove that properties that satisfy structures are formulas as they are a union of types.
Ehrenfeucht-Fraïssé Game
Also note $\alpha_K(\vec{x})$ is also $\text{FO}[k]$ formula.

---
From [[Ehrenfeucht-Fraïssé Game]] and the above theorem, we directly have 
>[!note] Theorem
>The equivalence relation $\equiv_k$ has a finite index.

---
# References
