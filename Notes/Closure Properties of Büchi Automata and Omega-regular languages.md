---
tags:
  - Note
---
202401121601

Tags : [[Automata Theory]]
# Closure Properties of Büchi Automata and Omega-regular languages
---
## Union
>[!tldr]
>The Union of two büchi automata can be done by just formally adding them.

Given $A=(Q_{A}, \Sigma, \Delta_{A}, I_{A}, F_{A})$ and $B=(Q_{B}, \Sigma, \Delta_{B}, I_{B}, F_{B})$ we can make 
$$
(Q_{A}\cup Q_{B},\; \Sigma,\; \Delta_{A}\cup \Delta_{B},\; I_{A}\cup I_{B},\ F_{A}\cup F_{B})
$$
This Büchi Automata accepts the union of the languages of $A$ and $B$

---
## Intersection
>[!tldr]
>The standard product construction of NFAs and regular languages also works for Büchi automata and $\omega$-regular languages. But we enforce that the final states are visited for both automata alternately. This condition is necessary and sufficient as for both automata, good states need to be visited infinitely many times.

- $Q' = Q_{A}\times Q_{B} \times \{ 1,2 \}$
- $I' = I_{A} \times I_{B} \times \{ 1 \}$
- $F' = (F_{A} \times Q_{B} \times \{ 1 \}) \cup (Q_{A} \times F_{B} \times\{2\})$
- $\Delta' = \Delta_{1} \cup \Delta_{2}$
	- $\Delta_1$ is taken when we are in states indexed by $1$ and we take transitions like $\Delta_A$. We change the index if we encounter a state in $F_A$.
	- $\Delta_2$ is taken when we are in states indexed by $2$ and we take transitions like $\Delta_B$. We change the index if we encounter a state in $F_B$.

$$
(Q',\;\Sigma,\;\Delta',\;I',\;F')
$$
---
## Right Concatenation with a Standard Regular Language(or Finite Automata)
>[!tldr]
>We get to jump to the Büchi Automata whenever we reach a final state in the finite automata.

- $Q' = Q_A\cup Q_C$
- $\Delta' = \Delta_A\cup \Delta_C\cup\Delta_{S}$
	- $\Delta_{S}=\{(q,a,q')|q'\in I_A\text{ and }\exists f:F_{C}\text{ such that }(q,a,f)\in \Delta_{C}\}$
- $F' = F_A$
- If $I_A\cap F_A$ is empty, then $I'=I_A$ otherwise its $I_A\cup I_C$.
---
## $\omega$-Closure
The proof for this is similar to the construction in [[Set of Languages accepted by Büchi Automata are exactly Omega-Regular]].

---
## Complementation
The proof for complementation is significantly harder than other closure properties.

>[!tldr]
>We break the language recognized by the automata into equivalence classes of standard regular languages and construct the complement using those.

We give an equivalence class over elements of $\Sigma^+$, such that for each $v, w$, we say $v\sim_A w$ if
- $\forall p q$, $v$ traces a path from $p$ to $q$  if and only if $w$ does too
- Furthermore, we make a similar condition for paths that contain good states.

>[!theorem] Lemmas
>[[Lemma 1 for Complementation of omega-Regular Languages|Lemma 1]]: $\sim_A$ has finitely many equivalence classes, all of which are regular languages.
>[[Lemma 2 for Complementation of omega-Regular Languages|Lemma 2]]: For each $w\in\Sigma^\omega$,  there are $\sim_A$ classes $L_1$ and $L_2$ such that $w\in L_1(L_2)^\omega$.
>[[Lemma 3 for Complementation of omega-Regular Languages|Lemma 3]]: If $L_1$ and $L_2$ are equivalence classes, then $L_1(L_2)^\omega$ is either a subset of $L_A$ or disjoint from it.


By using the above lemmas, we can get the finite set of equivalence classes ([[Lemma 1 for Complementation of omega-Regular Languages|Lemma 1]]) and partition them into ones that are disjoint from $L_A$ and ones that are a subset of it ([[Lemma 3 for Complementation of omega-Regular Languages|Lemma 3]]).  We know that these partition cover all of $\Sigma^\omega$ ([[Lemma 2 for Complementation of omega-Regular Languages|Lemma 2]]) so the first partition must be the complement of $L_A$ and we can construct a Büchi automata for it(like the constuction in [[Set of Languages accepted by Büchi Automata are exactly Omega-Regular]]).

>[!quote] Pravin
>I hope you notice the paradox here. There is no way to determine when this edge needs to be taken in the non-deterministic automata.

---
# References
- [[Omega-Regular Languages]]
- [[Büchi Automata]]
- [[Set of Languages accepted by Büchi Automata are exactly Omega-Regular]]
- [[Another way to Complement a Büchi Autromata]]