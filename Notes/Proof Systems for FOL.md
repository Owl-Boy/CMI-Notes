---
tags:
  - Note
  - Incomplete
---
202310101410

Tags : [[Logic]]

---
# Proof Systems for FOL
## Axioms
- All propositional axioms
- $A_{2a}:x\equiv x$ for all variables $x$
- $A_{2b}: t\equiv u \implies \varphi(t)\iff\varphi(u)$, where $\varphi$ is any atomic formula
- $A_{3}:\varphi(t)\implies\exists x\ \varphi(x)$

## Derivation rules
- Modus Ponens: $\dfrac{\varphi\ \varphi\implies\psi}{\psi}$
- Generalisation: $\dfrac{\varphi(x)\implies\psi}{\exists x\ \varphi(x)\implies\psi}x\not\in Fv(\psi)$

You can take a look at this [[Example for Proof System in FOL|example]]. 

---
## Soundness
If $X\vdash\varphi$ then $X\vDash\varphi$.

**Proof:** By induction on the length of the derivation $X\vdash\varphi$.



---
## Completeness
If $X\vDash\varphi$, then $X\vdash\varphi$.

**Proof:** $X\cup\{\lnot\varphi\}$ is not satisfiable. So $X\cup\{\lnot\varphi\}\cup\phi_{Q}\cup\phi_{\text{Eq}}\cup\phi_H$ is not propositionally satisfiable. So there is a finite subset $Y\subset X\cup\{\lnot\varphi\}\cup\phi_{Q}\cup\phi_{\text{Eq}}\cup\phi_H$ that is not satisfiable.

List the formulas in $Y$ as $\alpha_{1},\dots,\alpha_{n},\beta_{1},\dots,\beta_{m}$ as follows.
- $\alpha_{1},\dots,\alpha_{n}$ are formulas on $X\cup\phi_{Q}\cup\phi_{Eq}$, listed in any arbitrary order.
- $\beta_{1},\dots,\beta_{m}$ are from $Y\cup\phi_{H}$, listed *carefully*:
$L_H$ is the limit of $L_{0}\subset L_{1}\subset L_{2}\subset\dots$
For a formula $\psi$ over $L_{H}$, let the *rank* of $\psi$ be the least $i$ s.t. $\psi$ is a formula over $L_{i}$. The list $\beta_{1},\dots,\beta_{k}$ is s.t. $\text{rank}(\beta_{i})\ge\text{rank}(\beta_{i+1})$, for all $i\in\{1,\dots,m-1\}$.

A formula in $\phi_H$ is of the form $\exists x\ \psi(x)\implies\psi(c_{\psi(x)})$. Let's call $c_{\psi(x)}$ the *witnessing constant* of $\beta_{l}$. The witnessing constant of $\beta_{i}$ does not appear in $\beta_{i+1},\dots,\beta_{m}$.
$Y\cup\{\lnot\varphi\}$ is not propositionally satisfiable. So the following formula is valid, hence derivable.
$X\vdash\alpha_{1}\implies(\alpha_{2}\implies\dots\implies\alpha_{n}\implies\beta_{1}\implies\beta_{2}\implies\dots\implies(\beta_{m}\implies\varphi))$
We replace witnessing constants by variables:
$X\vdash\alpha'_{1}\implies(\alpha'_{2}\implies\dots\implies\alpha'_{n}\implies\beta'_{1}\implies\beta'_{2}\implies\dots\implies(\beta'_{m}\implies\varphi))$

$X\vdash\beta_{1}\implies(\beta'_{2}\implies\dots\beta'_{m})$


---
# References
