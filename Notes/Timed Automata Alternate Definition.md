---
tags:
  - Note
  - Incomplete
---
202311161611

Tags : [[Timed Automata]]
# Timed Automata Alternate Definition
---
## Syntax of Timed Automata

A *Timed Automaton* $\mathcal A$ is the tuple
$$
\mathcal A = \langle L, X, E, \mathcal I, \mathcal L\rangle
$$
- $L$ : Location / States
- $X$ : Clocks
- $E \subseteq L \times \mathcal G(X) \times \mathcal 2^X \times L$ : Edges
	- State + Guard + Resets -> State
- $\mathcal I : L\to \mathcal G(X)$ : Invariant 
- $\mathcal L : L\to\mathcal 2^{\text{AP}}$
	- $\text{AP}$ is a finite set of atomic propositions
	- Assignment of a logical proposition to each location.

---
## Semantics of Timed Automata
Semantics of a *Timed Automata* $\mathcal A$ is given by a labelled Transition system $T_{\mathcal A}$
$$
T_{\mathcal A} = \langle S, E \sqcup \mathbb R_{+}, \rightarrow \rangle
$$
- $S$ is a set of *states/symbolic states* $\{s=(l, \nu) \in L \times\mathbb R^{X}_{+}\;:\;\nu\vDash \mathcal I(l)\}$
- $\to$ is a transition function of type $S\times E \sqcup \mathbb R \times S$ composed of
	- *Delay transition:* $(l, \nu)\xrightarrow{\tau}(l, \nu+\tau)$ if $\tau\in \mathbb R_+$ and for all $0\le \tau'\le\tau$ we have $\nu + \tau'\vDash\mathcal I(l)$. Basically time is elapsed preserving the invariant.
	- *Discrete transitions:* $(l, \nu)\xrightarrow{e}(l',\nu')$ if $e=(l,g,T,l')\in E$ such that
		- $\nu \vDash \mathcal I(l) \land g$
		- $\nu' = [Y\leftarrow 0]\nu$
		- $\nu'\vDash \mathcal I(l')$

Also we define 
$$
\begin{align}
I(s,e) &= \{\tau\in \mathbb R_{+}\;:\;s\xrightarrow{\tau,e}s'\} &&\text{for some }s' \\
I(s)&= \bigcup_{e}I(s,e)
\end{align}
$$
$\mathcal A$ is said to be *non-blocking* if $I(s)\ne\emptyset$ for all $s$ ^15073a
### Runs
A *run* in a *timed automaton* is an alternating sequence of *delay* and *discrete* transitions written as 
$$
\varrho\quad:\quad s_{0}\xrightarrow{\tau_{1}} s_{1}'\xrightarrow{e_{1}}s_{1}\xrightarrow{\tau_{2}}s_{2}'\cdots\xrightarrow{e_{n}}s_{n}
$$
which can be written compactly as
$$
\varrho\quad:\quad s_{0}\xrightarrow{\tau_{1},e_{1}}s_{1}\cdots\xrightarrow{\tau_{n},e_{n}}s_{n}
$$
The set of runs in an automata $\mathcal A$ and starting at $s$ is written as $\text{Runs}(\mathcal A, s)$

### Symbolic Paths
A *Symbolic Path* is a set of *runs* starting at a *symbolic state* followed by a sequence of edges and restricted under some constraint $\mathcal C$. It is defined as
$$
\pi_{\mathcal C}(s,e_{1}\dots e_{n})=\{\varrho=s\xrightarrow {\tau_{1},e_{1}}\cdots\xrightarrow{\tau_{n},e_{n}}s_{n}\;:\;\varrho\in \text{Runs}(\mathcal A, s)\text{ and } (\tau_{i})\vDash\mathcal C\}
$$

---
# References
[[Region Automata Alternate Definition]]