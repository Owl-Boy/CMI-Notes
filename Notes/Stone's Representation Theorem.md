202308161610

type : #Example #Incomplete 
tags : [[Logic]]

#  Stone's Representation Theorem
---
### Theorem:
For every boolean algebra is isomorphic to a field of sets.
###  Proof:

---
### Theorem:
$\varphi$ is a classical tautology iff $\mathbb B\models \varphi$ for all [[Boolean Algebra|Boolean Algebras]] $\mathcal B$

### Proof:
The Implication from right to left is immediate.

For the other direction, **FTSOC** say $\mathcal{B}\not\models\varphi$ for some $\mathcal B$.
By **Stone's Representation Theorem** Every Boolean Algebra is a field of sets over some $X$.

Since $\mathcal B\not\models\varphi$, There is a valuation $v$ in $\mathcal B$ such that $\textlbrackdbl\varphi\textrbrackdbl_{v}\ne X$. Thus $\exists x\in X$ such that $x\notin\textlbrackdbl\varphi\textrbrackdbl_{v}$ 

Construct a valuation $w$ in $\mathbb{B}$ where $w(p)=1\iff x\in\textlbrackdbl p\textrbrackdbl_{v}$.
Then by induction on the size of $\varphi$ we get $w(\varphi)=1\iff x\in\textlbrackdbl\varphi\textrbrackdbl_{v}$

Thus $\textlbrackdbl\varphi\textrbrackdbl_{w}\ne 1$

---
# Related
[[Boolean Algebra]]
Bruh, Stone was a Chad: [Wiki](https://en.wikipedia.org/w/index.php?title=Marshall_H._Stone&useskin=vector)

