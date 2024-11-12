---
tags:
  - Note
  - Incomplete
---
202411101711

Tags : [[Set Theory]]
# Axiom of Constructibility
---
>[!definition] 
>*Axiom of Constructibilty* is the statement $\mathbf{V=L}$ which states that $L$ is the entire universe, aka the model. : 
>$$
>\forall x \exists \alpha (x\in L (\alpha))
>$$

To prove that one must first show that $x\in L(\alpha)$ is absolute.

We have that $\text{Df}$ is absolute, then $\mathcal D$ is absolute, and by transfinite recursion and the fact that ordinals are absolute, we have that $L(\alpha)$ is absolute for all transitive models of $\text{ZF}-\text{P}$.

with that we have the following 

>[!Theorem] Theorem(ZF)
>$\mathbf{L}$ is a model of $\text{ZF}+\textbf{V=L}$ 

If we relativize it to $L$ then we get the absoluteness because $\in$ is absolute. $\mathbf{ON}$ is absolute and as shown above $x\in L(\alpha)$ is absolute

>[!Theorem]
>If $\mathbf{M}$ is any transitive proper class model of $\text{ZF}-\text{P}$, then $\mathbf{L}=\mathbf{L^M}\subseteq \mathbf{M}$

Then we note that $\mathbf{ON} \subseteq \mathbf{M}$. Fix $\alpha$. Since $M\not \subset R(\alpha)$, there is an $x\in M$ such that $\text{rank}(x)\geq \alpha$. But the rank function is absolute for $\mathbf{M}$ so $\text{rank}(x)\in M$ therefore $\alpha\in M$ since $M$ is transitive.
Now by absoluteness of $L(\alpha)$ we define
$$
\mathbf{L^M}= \{ x \in \mathbf{M} : (\exists \alpha(x\in L(\alpha)))^\mathbf{M} \} = \cup \{ L(\alpha) : \alpha\in \mathbf{ON} \}=L.
$$



---
# References
[[Constructable Sets]]
[[L is a model of ZF]]