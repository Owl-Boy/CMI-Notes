---
tags:
  - Note
  - Incomplete
---
202309221209

Tags : [[Logic]]

---
# First Order Logic-Examples for Definability

Terms: $t = c|x|f(t_{1},\dots t_n)$
Formulas: $\phi = t_{1}\equiv t_{2} | R(t_{1},\dots t_{n}) | \lnot \phi | \phi \lor \phi | \exists x \phi$  

$L = (R,F,C)$
$R = \{< \text{binary}\}, F = \{\},C=\{\}$

1. $\phi: \forall x \forall y$  $(x<y)\lor(x\equiv y)\lor(y<x)$
$\mathcal{I}:$ $S=\mathbb{N}, <^{\mathcal{I}} (\text{usual order on }\mathbb{N})$

2. $\mathcal{I}:$ $S=\{a,b,c,d\},R=\{a<b,a<c,b<d,c<d\})$

- $\exists x \forall y (x \not\equiv y \rightarrow y<x)$ - There is a maximum element
- $\forall y \exists x(x \not\equiv y \rightarrow y<x)$ - Always true
- $\forall x \forall y \forall z ((x<y \land y<z) \rightarrow x<z)$ - Checks for transitivity
- $\exists x \forall y (x \not\equiv y \rightarrow x<y)$ - There is a minimum element (integers vs naturals)
- $\forall x \forall z \exists y ((x \not\equiv z) \rightarrow (x<y \land y<z))$ - Differentiates between rationals and integers

But we can't differentiate between $(0,\infty)$ and $(0,1)$ in the first order structure $(S_{i},<)$. In fact we can show an *isomorphism* between the two.

---
## Free variables

We will define by induction.
- $fv(\phi) \subset$ Var.
- $fv(t)=$ the set of all variables occurring in $t$
- $fv(t_{1}\equiv t_{2})=fv(t_{1})\cup fv(t_{2})$
- $fv(R(t_{1},\dots,t_{n}))=fv(t_{1})\cup\dots\cup fv(t_{n})$
- $fv(\lnot\phi) = fv(\phi)$
- $fv(\phi_{1}\lor\phi_{2})=fv(\phi_{1})\cup fv(\phi_{2})$
- $fv(\exists x \phi) = fv(\phi)\setminus\{x\}$

---
## Isomorphism

**Lemma:** Suppose $\phi$ is a FO formula. $\sigma_{1}$, $\sigma_{2}$ are s.t. $\sigma_{1}(x)=\sigma_{2}(x)$ for all $x \in fv(\phi)$. Then $(M,\sigma_{1})\models\phi$ iff  $(M,\sigma_{2})\models\phi$.
**Proof** by induction on the structure of $\phi$.

$\mathcal{I}_{1}=(M_1,\sigma_1)$
$\mathcal{I}_{2}=(M_2,\sigma_2)$
$\mathcal{I}_1$ and $\mathcal{I}_2$ are said to be isomorphic for $L=(R,F,C)$ if there is a bijection $\sigma$ : $S_{1}\to S_{2}$ s.t.
for every $r\in R$, $(e_{1,\dots})$

---
# References
[[Isomorphism Between First Order Interpretations]]