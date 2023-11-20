---
tags:
  - Note
  - Incomplete
---
 202311181611

Tags : [[Topology]], [[Probability]], [[Timed Automata]]
# Correspondence of Topological and Probabilistic Semantics for LTL
---
>[!info] Proposition
>Let $\mathcal A$ be a [[Timed Automata Alternate Definition#^15073a|Non-blocking Timed Automata]] and $\pi$ be an unconstrained symbolic path in $\text{R}(\mathcal A)$. 
>Then $\mathbb P_{\text{R}(\mathcal A)}(\pi) >0$ iff dimension of the path is defined

>[!note] Theorem
>Let $\mathcal A$ be a [[Timed Automata Alternate Definition#^15073a|Non-blocking Timed Automata]] and $s$ be a state in $\mathcal A$, and $\varphi$ be an [[Linear Temporal Logic|LTL]] formula, then 
>$$
>\mathcal A, s\mid\!\approx_{\mathbb P} \varphi \iff \mathcal A, s\mid\!\approx_{\mathcal T} \varphi
>$$

We prove the above theorem by proving the equivalence between the semantics on region automata, more over $\text{R}(\mathcal A),\iota(s)\mid\!\approx_\mathbb P \varphi$ iff $\mathbb P_\mathcal A(\iota(s),\lnot\varphi)=0$, this applying the above proposition gives us that $\text{R}(\mathcal A),\iota(s)\mid\!\approx_\mathbb P \varphi$ iff every symbolic path $\pi$ in $\text{R}_\mathcal A$ starting at $\iota(s)$ and satisfying $\iota$ has undefined dimension, and that is equivalent to  $\text{R}(\mathcal A),\iota(s)\mid\!\approx_\mathcal L \varphi$ or $\textlbrackdbl \lnot\varphi \textrbrackdbl=\{ \varrho \in \text{Runs}(\text{R}(\mathcal A), \iota(s))\;:\;\varrho \not\models\varphi \}$ is topologically *meager*.

So we prove the contrapositive version of the statement.

For the first implication we use [[Banach-Mazur Games]] and show that Player 2 has a winning strategy if the game is played on $\textlbrackdbl \lnot\varphi \textrbrackdbl$ 
Say Player 1 picked $\pi_1$. Since dimension of $\pi_1$ is defined so it satisfies $\varphi$. Then whatever is played afterwords, its intersection with the target will be empty so player 2 wins. So $\textlbrackdbl \lnot\varphi \textrbrackdbl$ is meager.

For the other way, assume $\textlbrackdbl \lnot\varphi \textrbrackdbl$ is meager. Since the topological space is a [[Baire Spaces|Baire Space]] we have $\text{Int}(\textlbrackdbl \lnot\varphi \textrbrackdbl)$ is empty. So there does not exist a path with defined dimension that satisfies $\lnot\varphi$.
And by the above proposition we get $\mathbb P_\mathcal A(\iota(s),\lnot\varphi)=0$.

$$
\textlbrackdbl \lnot\varphi \textrbrackdbl
$$

---
# References
