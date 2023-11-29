---
tags:
  - Note
---
202311300011

Tags : [[Logic]]
# Löwenheim-Skolem and its Variants
---
## Löwenheim-Skolem theorem

1. Suppose $X$ is a set of formulas that is satisfiable. If the logical language is countable (countably many constants (and functions and relations)), then $X$ has a (*at most*) *countable* model, i.e. there is a countable universe in which $X$ is satisfied.

**Proof:** Suppose $\mathcal{I}\vDash X$. Then $X\cup\phi_{Eq}\cup\phi_{Q}\cup\phi_{H}$ is propositionally satisfiable. So $X\cup\phi_{Eq}\cup\phi_{Q}\cup\phi_{H}$ is satisfiable in a countable model.

2. Suppose $X$ is a set of formulas over $L$ that is satisfiable, and $L$ is not countable. Then $X$ is satisfiable in a model which is *at least uncountable*.

```ad-info
title:
As a result of above, we can't define the set of real numbers in FOL using countably many constants.

```

## Variants of LS theorem
---

- If a set $X$ of formulas has finite models that are arbitrarily large (i.e. for every $n ∈ N$ there is a model for $X$ whose cardinality is at least $n$), then it also has a (*at least*) countable model.

**Proof:** Let $\lambda_{n}$ be the formula $\lambda_{n} = \exists x_{1}\dots x_{n}\bigwedge\limits_{\substack{i\neq j\\ i,j\in\{1,\dots,n\}}}x_{i}\not\equiv x_{j}$
($\lambda_{n}$ just says that there are at least $n$ distinct elements in the universe.)

$Y=X\cup\{\lambda_{n}|n\ge 1\}$.

(We construct this (at least) countable model. Every model for $Y$, if it exists, is countable. So we only need to prove its existence, aka satisfiability of $Y$.
We can do that by giving a model for each finite subset $X\cup{\lambda_{n}}$ is satisfiable and then compactness (finite-sat) go brr.)

### "Upward" LS theorem
---
Suppose $X$ has an infinite model. Then for every set $A$, $X$ has a model whose cardinality is at least that of $A$.

**Proof:** Similar to the proof above.

---
# References
[[First Order Logic]]
[[FOL Inexpressibility]]