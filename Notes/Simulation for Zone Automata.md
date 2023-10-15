---
tags:
  - Note
  - Incomplete
---
202310132310

Tags : [[Timed Automata]]

---
# Simulation for Zone Automata


```ad-tldr
In this approach we give a preorder between _symbolic states_ and we modify $\text{Trans}$ rule to not add an elment $q$ if we have aleady reached an element $p$ such that $p\succeq q$.

We the prove that this operation is finite, i.e, for all sequences $(q,Z_{1}), (q,Z_{2})\dots$, we have $(q,Z_{j})\preceq(q,Z_{i})$ if $i\le j$.
If the preorder is finite, then the forward analysis always terminates.
```

---
# References
