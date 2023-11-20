---
tags:
  - Note
  - Incomplete
---
202310101410

Tags : [[Logic]]

---
# A Proof System for FOL
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

```ad-hint
title: Motivation
We just need to prove that
- the axioms are true
- the derivation rules preserve validity (i.e. if a formula is valid, MP or Gen on it will be valid)

Then we look at the derivation of $\varphi$ from $X$ and be like every step in the derivation is either an axiom, which we have shown is sound, or uses previous stuff and a derivation rule, which we have also shown is sound.
```

**Proof:** By induction on the length of the derivation $X\vdash\varphi$.
- Propositional axioms:
  - $a\implies(b\implies a)$
  For every interpretation $\mathcal{I}$, we want to show that either $\mathcal{I}\vDash\lnot a$ or $\mathcal{I}\vDash\lnot b \lor a$.
  If $\mathcal{I}\vDash\lnot a$, we are done.
  Otherwise $\mathcal{I}\vDash a$ which implies $\mathcal{I}\vDash\lnot b\lor a$, and we are done.
  - $(a\implies(b\implies c))\implies((a\implies b)\implies(a\implies c))$
  For every interpretation $\mathcal{I}$, we want to show that either $\mathcal{I}\vDash a\land(b\land \lnot c)$ or $\mathcal{I}\vDash(a\land \lnot b)\lor(\lnot a \lor c)$.
  If $\mathcal{I}\vDash\lnot a$ or if $\mathcal{I}\vDash c$ we are done.
  So $\mathcal{I}\vDash a$ and $\mathcal{I}\vDash\lnot c$.
  If $\mathcal{I}\vDash b$, we are done, and so are we if $\mathcal{I}\vDash\lnot b$.
  - $(a\implies b)\implies((\lnot a\implies b)\implies b)$
  For every interpretation $\mathcal{I}$, we want to show that either $\mathcal{I}\vDash a\land \lnot b$ or $\mathcal{I}\vDash(\lnot a\land \lnot b)\lor b$.
  If $\mathcal{I}\vDash b$, then we are done.
  Otherwise, $\mathcal{I}\vDash\lnot b$. Now if $\mathcal{I}\vDash a$, we are done and so are we if $\mathcal{I}\vDash\lnot a$.
- $A_{2a}$
Given an interpretation $\mathcal{I}$, $\sigma(x)=e$ for some element $e$ in the universe, which is literally the same as saying $\sigma(x)=e$.
- $A_{2b}$
Suppose $\sigma(t)=e$, $e$ element in the universe. This means $\sigma(u)=e$. $\varphi^{\mathcal{I}}(t)=\varphi^{\mathcal{I}}(u)$.
- $A_{3}$




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
[[First Order Logic]]
[[Satisfiability in First Order Logic]]