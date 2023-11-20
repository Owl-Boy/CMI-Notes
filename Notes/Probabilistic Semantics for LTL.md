---
tags:
  - Note
  - Incomplete
---
202311172111

Tags : [[Timed Automata]], [[Probability]]
# Probabilistic Semantics for Linear Temporal Logic
---
The Interpretation of [[Linear Temporal Logic|LTL]] formulae happen over finite runs of a [[Timed Automata Alternate Definition|Timed Automata]].
The states in a run correspond to worlds used to define the semantics for *LTL*. And we use the function $\mathcal L$ in place of $\sigma$ to give the set of formulas satisfied by $s$.

>[!note] Intuition
> Since only the sequence of states corresponds to the [[Kripke Models|Kripke]] like structures used to give semantics to *LTL*, we can say that given a formula $\varphi$ and a path $\pi$, either all runs of $\pi$ model satisfy $\varphi$ or none of them do.
>Hence we can give a set of symbolic paths that satisfy the formula $\varphi$ and let the probability that $\varphi$ is true in the automaton be the probability that the set of paths can be taken.

more formally
$$
\mathbb P_{\mathcal A}(s_{0},\varphi)=\mathbb P_{\mathcal A} \{\varrho\in \text{Runs}(\mathcal A,s_{0})\;
:\;\varrho \models\mathcal\varphi\}
$$
and we say that $\mathcal A$ *almost surely satisfies* $\varphi$ from $s_0$ w.r.t $\mathbb P_\mathcal A$, and write $\mathcal A,s_0 \mid\!\approx_{\mathbb P} \varphi$ iff $\mathbb P_\mathcal A(s_0,\varphi)=1$.

Out Timed Automata Does not have a *Final State*, but it is easy to deal with it.
We add another $\text{acc}$ to the set of atomic propositions and assign it to each condition we want and define $\psi = \diamond \square \text{acc}$.
and instead of $\mathcal A,s_0 \mid\!\approx_{\mathbb P} \varphi$, we write $\mathcal A,s_0 \mid\!\approx_{\mathbb P} \varphi\mid\psi$

And from [[Probability Measure over Finite Paths in a Timed Automata#Similar Measures on $ mathcal A$ and $ textbf{R}_ mathcal A$|Lemma B]] we directly get that 
$$
\mathcal A,s_0 \mid\!\approx_{\mathbb P} \varphi \iff \textbf{R}_{\mathcal A},\iota (s_{0}) \mid\!\approx_{\mathbb P}\varphi
$$

---
# References
