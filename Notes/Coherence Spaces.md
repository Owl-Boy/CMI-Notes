202307281707

Type : #Note
Tags : [[Type Theory]], [[Category Theory]]

---
# Coherence Spaces
```ad-info
A **Coherence Space** is a set (of sets) $\mathcal A$ which satisfies:
- _Down Closure_: If $a\in\mathcal A$ and $a'\subset a$ then $a'\in\mathcal A$
- _Binary Completeness_: If $M\subset \mathcal A$ and $\forall a_{1},a_{2}\in M$ we have $a_{1}\cup a_{2}\in\mathcal A$, then $\bigcup M\in\mathcal A$
- $\emptyset\in\mathcal A$
```

for example
![[Pasted image 20230728172540.png]]

## Web
We define $|\mathcal A| = \bigcup\mathcal A=\{\alpha : \{\alpha\}\in\mathcal A\}$ and elements of $|\mathcal A|$ are called _Tokens_ of $\mathcal A$.
We then define a _Coherence Relation Module $\mathcal A$_ as follows
$$
\alpha\sim\alpha'\iff\{\alpha,\alpha'\}\in\mathcal A
$$
Which is an equivalence relation.
$|\mathcal A|$ along with the relation $\sim$ is called the **Web** of $\mathcal A$

Webs of $\mathcal {Bool}$ and $\mathcal{Int}$ are discrete graphs whose points are Booleans and Natural number respectively.

Construction of the **web** of a **coherence space** is a bijection to a graph, which is symmetric and transitive.

We can reconstruct the space by 
$$
a\in\mathcal A
\iff 
a\subseteq |\mathcal A|, 
\forall \{\alpha,\alpha'\}\subset a,\alpha\sim\alpha'
$$

---
# References
