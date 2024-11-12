---
tags:
  - Note
  - Incomplete
---
202411101511

Tags : [[Set Theory]]
# Definable Power Set
---
To make the class [[Constructable Sets|L]] of *Constructible sets* we will define a power set operation that will give the set of subsets of a $A$ that are definable by formulas relativized to $A$.

>[!definition]
>The *definable power set* $\mathcal D (A) = \{ X \subseteq A : \text{Cond} \}$, where $\text{Cond}$ is defined as:
>- $\exists n : \mathbb{N}$
>- $\exists s \in A^n$
>- $\exists  R \in \text{Df}(A, n+1)$
>- $(X=\{ x\in A : s\langle x\rangle \in R\})$

And we have the following lemma to let us construct sets corresponding to all possible formulae

>[!theorem] Lemma
>let $\phi(v_{0},v_{1}\dots v_{n-1}, x)$ be any formula with all free variables shown, then
>$$
>\forall A \forall v_{0},v_{1}\dots v_{n-1}\in A[\{ x\in A:\phi^A(v_{0},v_{1}\dots v_{n-1}, x) \}\in \mathcal D(A)]
>$$

The proof can be constructed directly from [[Definable Formulas#^6323ab| corresponding lemma for Definable Formulas]].

>[!theorem] Lemma
> For any $A$
>1. $\mathcal D(A) \subseteq \mathcal P(A)$
>2. If $A$ is transitive, then $A \subseteq \mathcal D(A)$
>3. All finite subsets of $A$ are in $\mathcal D(A)$
>4. $|A|\geq\omega \to |\mathcal D(A)|=|A|$

- 1 is trivially true. 
- For 2. we can a formula that states that the set is a subset of $A$.
- For 3, we know that the set is closed under union and intersection, we can consider a subset of $A^n$ defined by a formula that forces all components to be the same and then pick the first element. This gives a singleton set, and the collection of those, closed under union gives us all finite sets.
- For 4, we have $|A^n|=|A|$ whenever $|A|\geq\omega$. Since $|\text{Df}(A, n+1)|\leq\omega$, we have $|\mathcal D(A)|\leq |A|$

---
# References
[[Definable Formulas]]
[[Constructable Sets]]