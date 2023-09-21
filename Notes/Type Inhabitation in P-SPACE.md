---
tags:
  - Note
  - Incomplete
---
202309181409

Tags : [[Lambda Calculus]], [[Type Theory]]

---
# Type Inhabitation in P-SPACE
For every $L\subseteq\Sigma^{*}$ such that $L\in \text{PSPACE}$, there is an efficient $(\text{PTIME})$ $f:\Sigma^{*} \to \text{TQBF}$ such that such that
$$
\forall x\in \Sigma^{*}\iff f(x)\text{ is valid}
$$

for every $\Phi$, we will define $\Gamma_{\Phi}$ and $\alpha_{\Phi}$ such that $\Phi$ is valid iff $\Gamma_{\Phi}\vdash_{\text{NJ}(\to)}\alpha_{\Phi}$ 

Let $\text{Voc}(\Phi)$ be the set of propositional letters occurring in $\Phi$.
For every $p \in \text{Voc}(\Phi)$ let $\alpha_{p},\alpha_{\lnot p}$ be two propositional letters.
For every $\varphi\in \text{sf}(\Phi)$ let $\alpha_{\varphi}$ be a propositional letter.

```ad-todo
write types in $\Gamma_{\Phi}$ for logical operators
```
 

---
# References
