---
tags:
  - Note
  - Incomplete
---
202403131003

Tags : [[Complexity Theory]]
# Karp-Lipton Theorem
---
If $SAT$ has *polynomial size boolean circuits* then $PH=\Sigma_{2}^{P}$.

---
**Polynomial size circuits:**
$L\subseteq \{ 0,1 \}^{*}$ is said to have poly size circuits if there is a collection of boolean circuits $\{ C_{n} \}_{n\geq 0}$ s.t. $\forall n$ $size(C_{n}\leq p(n)$ ($p$ is some fixed polynomial).
$\forall n\ C_{n}$ is an $n-$input boolean circuit, and $L^{=n}=\{ x \in \{ 0,1 \}^{n}:C_{n}(x)=1 \}=L\cap \{ 0,1 \}^{n}$.

$L$ may have poly-size circuits but need not be even decidable!
eg. $L-$ Halting problem encoded in unary
This is the set $\{ 0^{\langle M,w \rangle}:M\text{ accepts }w \}$.
$L\subseteq 0^{*}\implies\ L$ has poly-size circuits.

$L\in P\implies\ L$ has poly-size circuits.
Because we know there is a $DTM$ for $L$ that runs in $p(n)$ time. Look at the run of the machine. Each new cell on the tape only depends on three cells in the previous tape (three or more, because it's not just binary at this point, because of alphabet etc(??), but it's still a constant). This $(a_{i},b_{i},c_{i})\mapsto(b_{i+1})$ can be encoded as a boolean circuit (as shown in the reduction to [[Circuit Value Problem]]). Thus $O(p^{2}(n))$ circuit exists for $L^{=n}$.

---
*Proof:*
We know that $\Sigma_{3}^{P}=\Sigma_{2}^{SAT}$. $(\star)$
Suffices to show $\Sigma_{3}^{P}=\Sigma_{2}^{P}$.

$L\in\Sigma_{3}^{P}$. Let $M$ be a $\Sigma_{3}^{P}$ machine accepting $L$.
On input $x$, $M$ will have the computation graph, with the top layer as the existential one, then a universal layer, and thirdly, an existential layer.

> [!question] What we want: to get a $\Sigma_{2}^{P}$ machine that accepts $L$.
> > [!hint] Strategy: Use $(\star)$ to get rid of the last $\exists$ layer.

So now we have in $M(x)$, an existential layer $(\exists y)$, and a universal layer $(\forall z)$, at the end of which we had a bunch of $\exists-$subgraphs, which we can now replace by $SAT$ instances $F_{x,y,z}$ following the [[Cook-Levin Theorem]] reduction, s.t. $M(x)$ accepts $x$ iff $\exists y$, $\forall y \in\{ 0,1 \}^{p(|x|)}$ s.t. $F_{x,y,z}\in SAT$, size (!??)

We can pad all the $SAT$ instances to make them all the same size.
The idea is to guess the circuit, say $C_{r}$, at the beginning (top of the first layer, so it is part of the first layer) and have only deterministic computations at the last layer. We need to then check 







---
# References
