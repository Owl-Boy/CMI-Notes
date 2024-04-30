---
tags:
  - Note
  - Incomplete
---
202402211202

Tags : [[Logic]], [[Automata Theory]]
# Büchi Automata for Linear Temporal Logic
---
As described in [[Semantics for LTL]], a structure for [[Linear Temporal Logic|LTL]] formula is defined by $\mathbb{N}\to 2^\mathcal P$ which is analogous to semantics for [[Büchi Automata|Generalized Büchi Automata]] which are runs that can be defined as $\mathbb{N}\to S$. 
Hence it is natural to construct a Büchi Automata over the vocabulary of a given formula. 

>[!tldr]
>We will show that sets of words constructed over $2^{\text{voc}(\varphi)}$ that correspond to structures that satisfy $\varphi$ form a Büchi recognizable set. 
>To be specific, 

---
## Construction of Büchi Automata

The set of states $S$ of the automata are exactly $\mathcal {AT}$ whose construction was discussed in [[Closure and Atoms for Büchi construction of LTL formulas]].

The Automata reads sets of atomic propositions $P\subseteq \text{voc}(\varphi)$. Then the transition $A\xrightarrow{P} B$ iff the following holds.
- $P\subseteq A\cap \text{voc}(\varphi))$
	- This is a sanity check, $P$ only contains atomic propositions that we care about, and it is read at a state which satisfies it.
	- This makes sure that the formula is propositionally satisfied
- For all $\bigcirc \beta\in \text{Cl}(\varphi)$, $\bigcirc\beta \in A$ iff $\beta \in B$
	- This conditions keeps the run consistent with the *next* operator.
	- It also keeps the run consistent with the *until* operator as the for every $\beta\ \mathcal U\ \gamma$ either the condition is satisfied by $\gamma$ in the atom. Or there will be a $\bigcirc(\beta\ \mathcal U\ \gamma)$. This does not guarantee the existence of $\gamma$ in some future state, that will be done by acceptance condition.

The start states $S_{\text{in}}= \{ A \in \mathcal {AT}\;|\;\varphi\in A \}$. This condition implies for every run, the corresponding structure will satisfy $\varphi$ at index $0$.

For each formula $\{ \beta_{1}\ \mathcal U\ \gamma_{1}\dots \beta_{n}\ \mathcal U\ \gamma_n\}$ which appear in $\text{Cl}(\varphi)$, we have the sets $(G_{1},G_{2}\dots G_{n})$ such that 
$$
G_{i} = \{ A\in \mathcal{AT}\;|\; \beta\ \mathcal U\ \gamma \not\in A \text{ or } \gamma\in A\}
$$
For each $\beta\ \mathcal U\ \gamma$ the acceptance condition ensures that it will be satisfied in the following way.
- $\beta \ \mathcal U\ \gamma\not\in A$.
	- This will happen only if the formula has been satisfied at some point before.
- $\gamma\in A$ 
	- This is for the case when $\beta \ \mathcal U\ \gamma$ will always be in the run except for finitely many atoms. This is still satisfiable if we see, $\gamma$ infinitely many times. Which is what this case covers.

---
>[!theorem]
>Let $M$ be an infinite word over $2^{\text{voc}(\varphi)}$. Then
>$$
>M\in L(\mathcal A_{\varphi}) \text{ iff } M,0 \models\varphi
>$$

The proof is a straightforward structural induction from left to right, and a straightforward induction on the run from right to left.

---
# References
[[Linear Temporal Logic]]
[[Büchi Automata]]