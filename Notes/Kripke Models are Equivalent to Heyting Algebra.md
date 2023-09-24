---
tags:
  - Example
---

202309111245

tags : [[Logic]]

#  Kripke Models are Equivalent to Heyting Algebra
---

Let $C$ be the set of all [[Filters in Heyting Algebras|prime filters]]  in $\mathcal H$, where $0\ne 1$. And let inclusion be the partial order. We define $F\Vdash p$ iff $\nu(p)\in F$ and we want to show that 
$$
F\Vdash\varphi
\iff 
\textlbrackdbl
    \varphi
\textrbrackdbl_{\nu} \in F
$$

The only non-trivial case is $\varphi = \varphi'\to\varphi''$
Suppose $F\Vdash f=\varphi'\to\varphi''$ but $\textlbrackdbl \varphi'\to\varphi''\textrbrackdbl_{\nu}=\textlbrackdbl \varphi'\textrbrackdbl_{\nu}\Rightarrow\textlbrackdbl\varphi''\textrbrackdbl_{\nu}$. So take the Smallest filter $G$ which contains $f$  and $\varphi'$.
And by [[Smallest Filter Heyting Algebras|Lemma 1]] we have $G = \{b\ :\ b\ge f\sqcap\varphi\text{ for some }f\in F\}$
And we have $\textlbrackdbl \varphi''\textrbrackdbl_{\nu}\notin G$ there is an $f$ where $\nu(\varphi'')\ge f\sqcup \varphi'$ , and this $\nu(\varphi'')\in F$ and we would be done.

By [[Extension of Proper Filter to Prime Filter in Heyting Algebras|Lemma 2]] we extend $G$ to a prime filter $H$ that does not contain $\nu(\varphi'')$. but $H$ contains $\varphi'$ and $\varphi'\to\varphi''$ and by primality it contains $\varphi''$ which is a contradiction.

For the converse assume we have $\nu(\varphi'\to\varphi'')$ and $F\subseteq H\Vdash\varphi'$ . And by induction hypothesis we have $\varphi'\in H$ and $\nu(\varphi')\Rightarrow\nu(\varphi'')$ so we have $\varphi''\in H$ and hence $H\Vdash \varphi''$.

Other cases are trivial, but primality is necessary for disjunctions.

---
# Related
[[Heyting Algebra]]
[[Kripke Models]]