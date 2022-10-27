202210111310

Type : #Note
Tags : [[Calc]]

---
# Determinants
let $V=\mathbb R^n$
$M_n\xrightarrow{\det}\mathbb R$ 
$M_n = \underbrace{R^n\times R^n\times\dots \times R^n}_{n \text{ times}}$
$(\overline{v_1},\overline{v_2}\dots\overline{v_n})\mapsto[\overline{v_1}|\overline{v_2}|\dots|\overline{v_n}]\mapsto\det[\overline{v_1}|\overline{v_2}|\dots|\overline{v_n}]$

_Proposition:_ Let $T:V\to V$ be a linear map. Given $w\in\Lambda^n(V)$
$w(Tv_1,Tv_2\dots Tv_n) = \det T\times w(v_1,v_2\dots v_n)$
_Proof:_ Choose a basis for $V$
let $w = \det$, $w(\overline{v_1},\overline{v_2}\dots\overline{v_n})=\det [\overline{v_1}|\overline{v_2}|\dots|\overline{v_n}]$
$w^T(\overline{v_1},\overline{v_2}\dots\overline{v_n}) = w(T\overline{v_1},T\overline{v_2}\dots T\overline{v_n})$
$w\mapsto w^T$ is a linear map $\Lambda^n V \to \Lambda^n V$.
$w^T(\overline{v_1},\overline{v_2}\dots\overline{v_n}) =\det[T\overline{v_1}|T\overline{v_2}|\dots|T\overline{v_n}]=\det\big(T[\overline{v_1}|\overline{v_2}|\dots|\overline{v_n}]\big)= \det T\times \det [\overline{v_1}|\overline{v_2}|\dots|\overline{v_n}]$
$\therefore w^T = \det T \times w$ for any $w$.



---
# Related Problems

---
# References
[[Exterior Algebra]]
