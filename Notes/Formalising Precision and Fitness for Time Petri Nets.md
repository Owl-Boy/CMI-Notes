---
tags:
  - Note
---
202405141505

Tags : [[Conformance Checking]]
# Formalising Precision and Fitness for Time Petri Nets
---
The notion of precision and fitness is given is very cleanly modelled using ideas of distance between trances as defined in [[Distance Functions for Timed Traces on Petri Nets]].

- **Fitness**: Given a model $N$ and a log $L$, we define fitness as $1-\max_\limits{l \in L} \text{Dist}^*(l, \mathcal L(N))$.
	- This can be interpreted as, drop in fitness corresponds directly to trances in the log, that are far away from what the model describes
	- The [[Alignments (Conformance Checking)|Alignments]] are witnesses for fitness measures.
- **Precision**: Given a model $N$ and a log $L$, we define precision as $1-\max_\limits{l \in \mathcal L(N)} \text{Dist}^*(l, L)$.
	- This can be interpreted as, drop in precision corresponds to the pathological behaviour of the model that does not fit the log.
	- The [[Anti-Alignments (Conformance Checking)| Anti-Alignments]] are witnesses for fitness measures.

---
# References
[[Distance Functions for Timed Traces on Petri Nets]]
[[Alignments (Conformance Checking)]]
[[Anti-Alignments (Conformance Checking)]]