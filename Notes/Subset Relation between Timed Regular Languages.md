202309051009

Type : #Note
Tags : [[Timed Automata]], [[Theory of Computation]]

---
# Subset Relation between Timed Regular Languages
**Theorem:** Let $\mathcal A$ be a _Timed Automaton_. The problem of checking whether $\mathcal L(\mathcal A)=T\Sigma^*$ is [[Turing Machines|Undecidable]].

**Proof:**
We will prove this by encoding the membership problem of a deterministic [[Counter Automata|2-counter machines]] as a _universality problem_.

We define a state of the counter automata as follows 
$$
(q,i,c,d)
$$
where $q$ is the state, $i$ is the position of the head on the tape, $c$ is the value of first counter and $d$ is the value of the second counter.

Here the first two components both have a _finite value_, hence a finite alphabet suffices to represent all pairs $(q, i)$ which will be read at integer time stamps.

The values of the counters are _countably infinite_. Hence we cannot do the same thing we did before, instead we add 2 new letters to the alphabet, which are $a_{c}, a_{d}$.
We accept $c_{i}$ many $a_{c}$ and $d_{i}$ many $a_{d}$ after accepting $(q_{i},i_{i})$ and before $(q_{i+1},i_{i+1})$.
To read the next state, we read $a_{c}$ again exactly after $1$ time unit and read an extra or skip reading one to represent increment and decrement of the counters.

A timed word $(\omega,\tau)$ over $\Sigma_\text{enc}$ encodes a run of a counter automata if
- Every integral point until the last time stamp contains a $(q, i)$ letter.
- At each $(i, i+1)$ the word is of the form $a_{c}^*a_{d}^{*}$. No two letters come at the same time stamp.
- The interval $[0,1)$ encodes the initial configuration.
- $[i,i+1)[i+1, i+2)$ encodes the appropriate transition given at $i$
- The last configuration should be accepting.

The idea is, we make a timed automata whose language is the complement of the above language, and checking of universality of the language gives membership of the counter automata which is undecidable.

To do that, we just make an automata to fail a condition for every condition, and then take the union of all of them.

```ad-todo
Make the automata for all the conditions.
```


---
# References
[[Untiming Timed Automata]]
[[Undecidability of the Membership Problem]]