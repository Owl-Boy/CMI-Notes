---
tags:
  - Note
---
202411021411

Tags : [[Set Theory]]
# Definable Formulas
---
>[!definition] Definable Formulas
>If $n \in \omega$ and $i, j<n$,
>1. $\text{Prog}(A, R, n)= \{ s \in A^n : \exists t \in R(t\upharpoonright n = s)\}$
>2. $\text{Diag}_{\in}(A,n,i,j)= \{ s \in A^n : s(i) \in s(j) \}$
>3. $\text{Diag}_{=}(A,n,i,j)= \{ s \in A^n : s(i) = s(j) \}$
>4. By recursion on $k \in \omega$, we define a helper $\text{DF}'(k, A, n)$ for all $n$ simultaneously by:
>	1. $\text{Df}'(0, A, n)= \{ \text{Diag}_{\in}(A,n,i,j) : i \leq j \} \cup \{ \text{Diag}_{=}(A,n,i,j) : i \leq j \}$
>
>
>	1. $\begin{align}\text{Df}'(k+1, A, n) &= \text{Df'}(k, A, n) \cup \{ A^n \setminus R : R\in \text{Df}'(k, A, n)\}\\ &\cup \{ R \cap S : R, S\in \text{Df}'(k, A, n) \} \\ &\cup \{ \text{Prof}(A, R, n): R \in \text{Df}'(k, A, n+1) \}\end{align}$
>5. $\text{Df}(A, n) = \bigcup \{ \text{Df}'(k, A, n): k\in \omega \}$

>[!idea] Interpretation of the above definition
>$\text{Diag}_{\in}$ lets us construct formulas that contain $\in$ symbol, while $\text{Diag}_{=}$ lets us check for equality. This along with the closure under complement and union and intersection gives us access to basic formulas that can be constructed using the language of set theory.
>Closing it under projection lets us define complex fromulas with fewer variables too.
>
>If fact, the next theorem tells us that every formula relativized to a set $A$ with $n$ variables belongs to $\text{Df}(A, n)$

>[!theorem]
>Let $\phi(x_{0},\dots x_{n-1})$ be any formula whose free variables are among $x_{0}\dots x_{n-1}$, then
>$$\forall A[\{ s \in A^n : \phi^A(s(0)\dots s(n-1))\} \in \text{Df}(A, n)]$$

^6323ab

The proof is by induction on the length of $\phi$, all atomic formulas of the form $x_{i}=x_{j}$ and $x_i \in x_{j}$ are definable, and they are also closed under all logical connectives. And the projection lets us deal with $\exists y$ for $y$ not any of $x_{0}\dots x_{n-1}$.

---
# References
[[Definable Formulas are Countable]]
[[Definable Power Set]]
[[Constructable Sets]]