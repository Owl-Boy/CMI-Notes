---
tags:
  - Example
---

202402281729

tags : [[Automata Theory]]

#  Last Appearance Record
---
>[!idea]
>We keep track of the states that are visited most recently states in order. And we have an extra marker to indicate which state was just reached. This gives us enough information to construct a Rabin Automata accepts exactly a given set of words.

This is a construction from a *Deterministic Muller Automata* to a *Deterministic Rabin Automata*.  

---
## Set of States

Let $S$ be the set of states of the Muller Automata $\mathcal M$.
Then the set of states of the Rabin Automata $\mathcal R$ is given by $S! = \{ \text{permutations of states in }S\cup\{\natural\} \}$. So each state is an $n+1$ tuple where $n=|S|$.

## Start State
If $s$ is a starting state of $\mathcal M$ then any arbitrary tuple with its first component $s$ can be thought of as a starting state.

## Transition
The goal is to simulate a transition of $\mathcal M$ in $\mathcal R$. We do that by treating the first component of the current state of $\mathcal R$ as the current state of $\mathcal M$ in the component.

Given a transition $(s, a, s')$ in $\mathcal M$ we get the following transition in $\mathcal R$ :=
$$
(s, x_{1},x_{2},\natural,x_{3}\dots x_{k},s'\dots x_{n}) \xrightarrow{a}(s',s,x_{1}\dots x_{k},\natural,x_{k+1}\dots x_{n})
$$
Here the $\natural$ denotes the previous position of $s'$ in the tuple.

## Acceptance Condition
Given a set of state, we want to make sure we visit all states in the set infinitely many times, and we visit all other states at most finitely many times.

For a given $F_i$ for $\mathcal M$, we get the following bad states
$$
B_{i} = \{ s_{1}\dots \natural\dots s_{n}\quad|\quad s_{1}\not\in F_{i} \}
$$
Reaching a bad state in $\mathcal R$ means reaching a state not a part of $F_i$ in $\mathcal M$, hence these states should only be visited finitely many times.

And these are the good states
$$
G_{i} = \{ f_{1}f_{2}\dots f_k\natural s_{1}\dots s_{n-k}\quad|\quad f_{1}f_{2}\dots f_{k} \in F_{i}!\}
$$
The good states make sense if we assume that the bad states are reached finitely many times.
If we assume that, we can just look at the part of the good states up to $\natural$ because the rest of it will not be touched after some finite amount of steps.

Here the $\natural$ goes to the last position infinitely many times. That means the state in the last position is sent to the first position infintely many times.

Since the number of states are finite, without loss of generality we say that $f$ is moved from the end to the beginning infinitely many times.

But once $f$ is in the front, for it move to the end, all other states must be visited before $f$. Hence all the states are visited infinitely often.

---
# Related
[[Another way to Complement a Büchi Autromata]]
[[omega-Automata]]