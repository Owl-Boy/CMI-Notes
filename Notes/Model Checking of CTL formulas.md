---
tags:
  - Note
---
202404171204

Tags :[[Logic]]
# Model Checking of CTL formulas
---
>[!question] Model Checking
>Given a Kripke Structure $\kappa$ and a CTL form $\psi$, does $\kappa$ satisfy $\psi$? 

## Simpler Fragment
To make our life easier, we will restrict the subset of formulas of *CTL* formula to a smaller subset which is just as powerful and is given by
$$
\Psi :=
\begin{matrix}
&\top &| &p &|& \lnot \Psi &| &\Psi \lor \Psi \\
&E X \Psi& |& E(\Psi U \Psi) &|& E G \Psi
\end{matrix}
$$
Notably, this fragment just gets rid of the universal path quantifier and propositional conjunction, both of which can be easily emulated form the given fragment, hence a model checking algorithm for this fragment gives a model checking algorithm for *CTL*

## Model Checking Algorithm 
The model checking algorithm is a [[P Complexity Class|Polytime Algorithm]] that checks if every state in the kripke structure $\kappa$ satisfies $\psi$. 

This is like a dynamic programming algorithm where we start verifying from the atomic formulas in $\psi$ and the combining that to build more and more complicated subformulas until we get to $\psi$ itself, this will be done by having a representing set of each subformula of $\psi$ that will be used to build one for $\psi$ given by the following rules.

1. All states satisfy the formula $\top$
2. Given a state $s$ and a propositional formula $p$, we say that  $s$ satisfies $p$ by using the labelling function, i.e $s\Vdash p$. (from now this symbol will be used for states satisfying CTL formulas as well). Doing this gives the subset $S_{p}$ of states that satisfy the propositional formula $p$.
3. After computing the state $S_{\phi}$ for some $\phi$ we get $S_{\lnot\phi}=\overline{S_{\phi}}$
4. $S_{\phi_{1} \lor \phi_{2}} = S_{\phi_{1}} \cup S_{\phi_{2}}$
5. $S_{EX\ \phi}$ is the set of states for which there is a successor that satisfies $\phi$ hence can be given by $S_{EX\ \phi}=\{ s\;|\;\text{next}(s) \cap S_{\phi} \neq \emptyset \}$
6. $S_{E(\phi_{1}\ \mathcal U\ \phi_{2})}$ is the set of states from where there is a path to something in $S_{\phi_{2}}$ that completely remains inside $S_{\phi_{1}}$, this can be done in the following way
	1. Let the set $S_{E(\phi_{1}\ \mathcal U\ \phi_{2})}=S_{\phi_{2}}$
	2. Add all states $s$ such that $s \in S_{\phi_{1}}$ and $\text{next}(s) \cap S_{E(\phi_{1}\ \mathcal U\ \phi_{2})}\ne \emptyset$
	3. Keep repeating till a fixed point is reached. (This can also be thought of as a BFS algorithm)
7. $S_{EG\ \phi}$ is the set of states from which there is an infinte path that satisfies $S_{\phi}$, this can found in the following way
	1. Let $S_{EG\ \phi}=S_{\phi}$
	2. Remove any element $s$ of $S_{EG\ \phi}$ such that $\text{next}(s) \cap S_{EG\ \phi}= \emptyset$
	3. Keep repeating till a fixed point is reached.

Given the above set of rules we do the following.
Let $\Phi$ be the set of all subformula for $\psi$ with a "subformula ordering"
- We do a toposort on the DAG derived from the above set with ordering.
- We then move from the greatest element to the lowest elements finding the corresponding representative set for each subformula, this is the part of the algorithm that represents dynamic programming.

---
# References
[[Kripke Models]]
[[Computation Tree Logic|CTL]]