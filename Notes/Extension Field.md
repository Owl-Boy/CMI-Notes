202210121010

Type : #Note
Tags : [[Algebra]]

---
# Extension Field
If $K$ is a field containing the sub field $F$, then $K$ is said to be an extension
field (or simply an extension) of $F$, denoted $K / F$ or by the diagram
$$
\begin{matrix}
K\\
\huge|\\
F
\end{matrix}
$$

$F$ is sometimes called the _base field_ of the extension.

```ad-note
The notation $K/F$ is short hand for "$K$ over $F$" and not quotient of $K$ by $F$
```

The _Degree_ of the field extension $K/F$, denoted by $[K:F]$, is the dimension of $K$ as a vector space over $F$. The extensions is said to be finite if $[K:F]$ is finite, infinite otherwise.
 
_Theorem:_ Let $F$ be a field and $p(x)\in F[x]$ be irreducible, then there exists a field $K$ containting an isomorphic copy of $F$ such that $p(x)$ has a root in $K[x]$. 
_Proof:_ Consider the quotient:
$$
K = F[x]/(x^2+1)
$$
Since $x^2+1$ is irreducible $(x^2+1)$ is a maximal ideal. Hence, $K$ is a field.
Let $\pi:F[x]\to K$ be the canonical projection. Then $\pi|_{F}:F\to K$ is a field homomorphism.
Since it is not identically $0$ $K$ contains and isomorphic copy of $F$.
Let $F$ be identified with its isomophic copy in $K$, then we can view $K$ as an extensions of $F$
let $\overline x = \pi(x)$
$$
\begin{aligned}
p(\overline x) &= \overline{p(x)} &(\text{Since $\pi$ is a homomorphism})\\
&= p(x) \mod p(x) &(\text{in }F[x]/p(x))\\
&= 0
\end{aligned}
$$

Hence $K$ contains a root of $p(x)$

_Theorem:_ let $L\subseteq K\subseteq F$ be fields then
$$
[L:F] = [L:K][K:F]
$$
i.e the degree of the extension is multiplicative.


---
# Related Problems

---
# References
[[Fields]]