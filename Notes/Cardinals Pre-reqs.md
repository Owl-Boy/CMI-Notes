---
tags:
  - Note
---
202408291608

Tags : [[Set Theory]]
# Cardinals Pre-reqs
---
**Cardinals** are a structure used to formalise the idea of "size" or a set.

This note will only use $ZF^- -P$. That is, we assume all except Foundation, Choice and Power. Since we do not have power, we cannot construct cardinals larger than $\aleph_0$ and without choice, we cannot in general define the size $|X|$ of an infinite von Neumann cardinal.

>[!theorem]
>If $B\subseteq A$ and $f :A \xrightarrow{1-1}B$ then $A\approx B$ 

We have 
$$
f^0(A)=A \supseteq f^0(B) = B \supseteq 
f^1(A)\supseteq f^1(B) \supseteq 
f^2(A)\supseteq f^3(B) \supseteq 
f^3(A) \dots
$$

Let
- $H_n= {f^n(A)} \setminus f^n(B)$ 
- $K_n = f^n(B)\setminus f^{n+1}(A)$
- $P = \bigcap_{n < \omega} H_n = \bigcap_{n < \omega} K_n$

We have 
$$
\begin{matrix}
A & = & P & \sqcup & H_{0}\sqcup H_{1}\sqcup H_{2}\dots & \sqcup & K_{0}\sqcup K_{1} \sqcup K_{2} \dots\\
B & = & P & \sqcup & H_{1}\sqcup H_{2}\sqcup H_{3}\dots & \sqcup & K_{0}\sqcup K_{1} \sqcup K_{2} \dots\\
\end{matrix}
$$

And all of the sets are pairwise disjoint then we let $g(x) = f(x)$ forall $x \in \bigcup_{n} H(n)$ and $g(x) = x$ otherwise. This gives $g : A\xrightarrow[\text{onto}]{1-1} B$.

>[!theorem] Schroder-Bernstein Theorem 
>$A\approx B$ iff $A \preceq B$ and $B\preceq A$

Left to right is trivial. The other direction can be proved using the previous lemma.

>[!theorem] Cantor
>If $\mathcal{P}(A)$ exists, then $A \prec \mathcal P(A)$

$A\preceq \mathcal P (A)$ because of the map $x \mapsto \{ x \}$ defines an injection from $A$ to $\mathcal P(A)$. Equality does not because if there is a bijection, consider the set $D = \{ x \in A : x \not\in f(x)  \}$. Then there is no element can map to $D$.

>[!Theorem]
>- $B \subseteq \alpha \to \text{type}(B; \in) \leq \alpha$
>- $\beta\preceq \alpha$ then $\beta \approx \delta$  for some $\delta \le \alpha$
>- If $\alpha \leq \beta \leq \gamma$ and $\alpha \approx \gamma$ then $\alpha \approx \beta \approx \gamma$



---
# References
[[Von Neumann Ordinals]]