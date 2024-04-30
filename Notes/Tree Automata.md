---
tags:
  - Note
  - Diagram
---
202404221904

Tags : [[Automata Theory]]
# Tree Automata
---
>[!tip] Why Trees
>Trees are a way to represent information in a fairly well structured way, a lot of times even strings semantically represent, like : 
>- `5 + 3 * 7`
>- `a \/ b /\ ~c`
>- Document formats like HTML and XML are also string representation of a tree structure
>
>These are likely to arise when the input has a structure more complicated than just a total order, hence a we study models that talk directly about trees.
>
>Notation and details about trees are discussed in [[Trees (Automata Theory)]]

>[!Attention] The two ways to think about transitions
>Sir has defined a transition to the set $\mathbb{N}\times S$ whereas I like to think of it as $[S]$  so I will be using that for this note. The two notations are obviously equivalent where a list can just be denoted as a bunch of $\mathbb{N} \times S$, one for each place and a $(n, s)$ can be denoted as $[-\dots -,s,-\dots -]$ .

The Automata reads $\Sigma$-labelled $k$-ary trees, with $Q$ as the set of states and $F$ be an accepting subset of the states what is non-trivial is the transition, given a state and a letter read at the state, the run of the automata should go to a list of states whose count is decided by the number of children of the input tree at that node hence we define $\delta(q, \sigma) = \bigcup_{i\in [0..k]}\delta(q, \sigma, i)$ where $\delta(q, \sigma, i)$ is an $i$-element list of states for deterministic automata denoted by $[Q; i]$. So we have the following

>[!definition] Deterministic Case
>A Deterministic Tree Automata is the following quadruple
>$$
>\mathcal T = \langle Q, \Sigma, Q_{F}, \delta \rangle
>$$
>where
>- $Q$ is the set of states
>- $\Sigma$ is the alphabet of the tree
>- $Q_{F}$ is the set of final states
>- $\delta : Q \times \Sigma \to [Q] = \bigcup_{i \leq k}\delta_i$
>	- $\delta_{i} : Q \times \Sigma \to [Q; i]$
>	- That is, it goes from a state to a list of $i$ states after reading a letter.

---
## Runs

We give the location of the state in terms of $w\in\mathbb{N}^*$.

A run of a tree automata is a *tree* that follows the following conditions
- Given a state $T_{\text{inp}}(w)$, and the corresponding states $T_A(w)$ in the unfolding of the automata, If the list of children has of $T_{\text{inp}}(w)$ has $m$ elements, then the next list of states is decided by $\delta_m(T_A(w), T_{\text{inp}}(w))$.
- This means that for a state in the run of the tree, it has the same number of children as that of the input character that will be read.

The accepting conditions are similar to as described for automata on words, and a tree is accepted if every path from the root to each leaf is accepted.

>[!todo] Diagram : Sreevani

---
## Variants
Corresponding to different flavours of automata over words we have multiple variants of automata over trees

- **Non-Determinism**: We let the range of $\delta_i$ be $2^{[Q;i]}$ 
- **Alternation**: We let the range of $\delta_i$ be $\mathbb{B}^+([Q;i])$
- **Acceptance**: We can use other kinds of acceptance conditions, like the omega-acceptance conditions to make tree automata over infinite trees. 

---
# References
[[Trees (Automata Theory)]]