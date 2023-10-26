---
tags:
  - Note
---
202310121910

Tags : [[Timed Automata]]

---
# Monolithic Timed Automaton for a Network of Timed Automata

Given a [[Networks of Timed Automata|Network of Timed Automata]], we want to be use all the tools constructed for *Timed Automata* to analyze it. One the things which we might want to analyze is reachability of states to ensure that none of the problematic states are reachable, or that an important state is.

One way to do that is to Construct a single timed automaton that corresponds to the network and analyze that.

The following construction will represent all possible combinations of states as tuples, and transitions would be build using transitions between the component states.

Consider the network $\langle \mathcal A_{1},\mathcal A_{2}\dots \mathcal A_{k}\rangle$.
We construct and automata $\mathcal A$ as follows
- $Q = \prod Q_{i}$, which makes the set of states.
- $S = \prod S_{i}$ is the set of starting states.
- $F = \prod F_{i}$ is the of final states.
- $\Sigma = \bigcup \Sigma_{i}$ which is the Alphabet.
- $X = \bigsqcup X_{i}$ which is the set of clocks.

For the transitions, we need to be careful about synchronizations.

Given a state $\langle p_{1}, p_{2}\dots p_{k}\rangle$ and a letter $\alpha$. Without Loss of dots generality, let $\alpha\in \Sigma_{1}\dots \Sigma_{i}$ and $\alpha\notin \Sigma_{i+1}\dots \Sigma_{k}$.
If There exists transitions from $p_{x}$ to $q_{x}$ accepting $\alpha$ with guard $G_x$ and resets $R_{x}$ for all $x\le i$. we can make the transition from $\langle p_{1}\dots p_{i},p_{i+1}\dots p_{k}\rangle$ to $\langle q_{1}\dots q_{i},p_{i+1}\dots p_{k}\rangle$ accepting $\alpha$ with guards $\bigwedge\limits_{x\le i}G_{x}$ and resets $\bigsqcup\limits_{x\le i}R_{x}$.

```ad-warning
The number of states this leads to is $\prod |Q_{i}|$ which gets big very quickly. Evaluating the states lazily can give significantly better results.
```

---
# References
[[Networks of Timed Automata]]