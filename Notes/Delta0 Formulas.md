---
tags:
  - Note
  - Incomplete
---
202410211110

Tags : [[Set Theory]], [[Logic]]
# $\Delta_{0}$ Formulas
---
$\Delta_{0}$ formulas are a part of the [[Levy Hierarchy]] that was constructed to have easy examples of absoluteness results that make relative consistency results easier to talk about.

>[!definition]
>- All Atomic formulas are $\Delta_{0}$ formulas
>- If $\varphi_{0}$ is a $\Delta_{0}$ formula, $y$ is a free variables in $\varphi_{0}$ and $\tau$ is a term that does not contain $y$ then $\forall y\in \tau, \varphi_{0}$ and $\exists y \in \tau, \varphi_{0}$ are $\Delta_{0}$ formulas
>- If $\varphi$ is a $\Delta_{0}$ formulas, so is $\lnot \varphi$
>- If $\varphi$ and $\phi$ are $\Delta_{0}$ formulas then so are $\varphi \land \phi$, $\varphi \lor \phi$, $\varphi \to \phi$ and $\varphi \iff \phi$.

When $\mathcal L = \{ \in \}$ the many basic concepts of set theory can be expressed as $\Delta_{0}$ formulas, for example
- $x \subseteq y$ can be written as $\forall z \in x [z\in y]$
- $x =  \emptyset$ can be written as $\forall z \in x(\bot)$
- $\text{Sing}(x)$ can be written as $\forall y\in x, z\in x [y=z]$.

---
# References
[[First Order Logic]]