---
tags:
  - Note
  - Incomplete
---
202310132210

Tags : [[Timed Automata]]

---
# Extrapolation for Zone Automata

```ad-tldr
The purpose of *Extrapolation* is to ensure a finite number of _symbolic states_ using an approach which is similar to [[Region Automata]]. 

We produce an operator $\text{extra}$ which extends the zone of a symbolic state, and we change to $\text{Trans}$ rule to accomodate that.
Then we show that the rand of the operator is finite, that is for all infinte sequences $Z_i$ of zones we find $\text{extra}(-,Z_{i+k})\subseteq\text{extra}(-,Z_{i})$ .
This will directly give the termination of forward analysis.
```

---
# References
