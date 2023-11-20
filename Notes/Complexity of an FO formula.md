---
tags:
  - Note
  - Incomplete
---
202310171410

Tags : [[Logic]]

---
# Complexity of an FO formula
We will call this the *Quantifier rank* of the FO formula.

$qr(\varphi)$

$qr(t_{1}\equiv t_{2})=qr(r(t_{1},\dots,t_{n}))=0$
$qr(\lnot\varphi)=qr(\varphi)$
$qr(\varphi_{1}\lor\varphi_{2})=qr(\varphi_{1}\land\varphi_{2})=\max(qr(\varphi_{1}),qr(\varphi_{2}))$
$qr(\exists x\ \varphi)=qr(\forall x\ \varphi)=qr(\varphi)+1$

---
# References
[[First Order Logic]]
[[FOL Inexpressibility]]
