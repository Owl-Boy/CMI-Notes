---
tags:
  - Example
---

202310101437

tags : [[Logic]]

# Example for Proof System in FOL
---

We want to prove $t\equiv t$.
1. $x\equiv x$
2. $y\equiv y$
3. $\lnot(x\equiv x)\implies\lnot(y\equiv y)\quad(1,PL)$
4. $\exists x\ \lnot(x\equiv x)\implies\lnot(y\equiv y)\quad(3,G)$
5. $\lnot(t\equiv t)\implies\exists x\ \lnot(x\equiv x)\quad(A_{3})$
6. $\lnot(t\equiv t)\implies\lnot(y\equiv y)\quad(4,5,PL)$
7. $t\equiv t\quad(6,2,PL)$

---
# Related
