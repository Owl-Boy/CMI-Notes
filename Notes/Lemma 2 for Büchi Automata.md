---
tags:
  - Example
---

202401122346

tags : [[Automata Theory]]

#  For each $w\in\Sigma^\omega$,  there are $\sim_A$ classes $L_1$ and $L_2$ such that $w\in L_1(L_2)^\omega$.
---
For this part we use the [Infinte Ramsey's Theorem](https://en.wikipedia.org/w/index.php?title=Ramsey%27s_theorem&useskin=vector#Infinite_Ramsey_theorem).
Let $w=a_0a_1\dots$ and let $w(i,j)=a_i\dots a_{j-1}$.

We let equivalence classes of $\sim_A$ be the colour of subsets of $\mathbb{N}$.

We colour $\{i,j\}$ if $i<j$ by the equivalence class that $w(i,j)$ belongs to.

We can now find a subset $X\subseteq \mathbb{N}$ such that each subset of size $2$ of $X$ has the same colour.

Let $0<i_1<i_2\dots\in X$. so all $\{i_k,i_{k+1}\}$ have the same colour, which means all $w(i_k,i_{k+1})$ belong to the same class.
We let the class of $w(0, i_1)$ be $L_1$ and the class of every $w(i_{k},i_{k+1})$ be $L_2$.

Then $w\in L_1(L_2)^\omega$.

---
# Related
[[Lemma 3 for Büchi Automata]]
[[Lemma 1 for Büchi Automata]]