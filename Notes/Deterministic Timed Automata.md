202309071009

Type : #Note 
Tags : [[Timed Automata]]

---
# Deterministic Tomato
```ad-info
title: Determinisitc and Complete Automata
A *Deterministic Automaton* is an Automaton such that it has a unique start state and for each letter of the input alphabet, there is at most 1 transition for each letter in the alphabet for each state.

An automaton is called *Complete* if for each state, there is a transition for each letter.

*Deterministic* along with *Complete* implies that there is a unique run for each letter.
```


For a *Timed Automata*, The deterministic condition holds if from a state, all transitions that accept a letter have guards which are never pairwise mutually satisfiable. And Completeness condition holds when the union of all the guards always holds.

## Closure Properties
Complete and Deterministic Timed Automata are closed under
- **Union**
The union of two complete and deterministic timed automata $\mathcal A_1$ and $\mathcal A_2$ is
$$
\begin{align*}
\mathcal A &= \langle \Sigma,L, l, C, F, E\rangle\\
\Sigma&= \Sigma_{1}\cup\Sigma_{2}&\text{Alphabet}\\
L &= L &\text{States}\\
l &= (l_{1}, l_{2}) & \text{Start State}\\
C &= C_{1}\sqcup C_{2} & \text{Clocks}\\
F &= \{(a, b)\ :\ a\in F_{1}\lor b\in F_{2}\} &\text{Final States}\\
E &= \{\langle(a_{1,}a_{2}),\alpha,B_{1}\land B_{2,}R_{1}\cup R_{2}, (b_{1},b_{2})\rangle\} &\text{Transitions}
\end{align*}
$$
where $\langle a_{i}, \alpha,B_{i},R_{i},b_{i}\rangle, i\in \{1,2\}$ are transitions in $A_{i}$ 

- **Intersection**
The Intersection of two automata $\mathcal A_1$ and $\mathcal A_{2}$ is given by an almost identical construction except $F = \{(a, b)\ :\ a\in F_{1}\land b\in F_{2}\}$

- **Complement**
The Complement of a complete and deterministic timed automata can be made done by making the accepting states non accepting and vice versa

These construction are essentially the same as the ones for Untimed DFAs

```ad-question
title: Determinizability
Since Not all Timed Automata are Determinizable(complement closure). Then given a timed Automata is its determinizability decidable.

Spoiler : Nope
```

## Examples
$\{a^{k}, \tau_{1},\tau_{2}\dots \tau_{k}\ :\ \tau_{k}-\tau_{k-1}=1\}$ where $k\ge 2$ 
![[Drawing 2023-09-07 12.51.29.excalidraw]]


---
# References
[[Event Recording Automata]]