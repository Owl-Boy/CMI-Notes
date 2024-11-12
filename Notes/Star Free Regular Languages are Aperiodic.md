---
tags:
  - Note
  - Incomplete
---
202411120011

Tags : [[Algebraic Automata Theory]]
# Star Free Regular Languages are Aperiodic
---
The idea is to show that all operations in the grammer can be simulated by an Aperiodic Monoid.

- Negation is handled because languages recognized by are closed under boolean operations
- Union of languages can also be handled similarly
- Single letter languages can also be easily recognized by the monoid $\{ 0,1,a \}$.
- Empty language is trivially accepted
- Empty words are also trivial
- Concatenation is the only non-trivial case, this is because for an aperiodic monoid, there exists $n$ such that for all $x$,  $x^n=x^{n+1}$. Let $N$ be twice the greater one of those $n's$ between the two automata. Given any word of the form $w x^{a}y$, where $a > N$, we can split the word in 2 parts such that at least one of the parts is more than $\frac{N}{2}$, so one can shrink that part down, which gives an equivalence class on words that can be used to construct an aperiodic monoid.
---
# References
