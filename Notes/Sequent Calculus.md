---
tags:
  - Note
---
202310120910

Tags : [[Logic]]

---
# Sequent Calculus
```ad-quote
title: Gerhard Gentzen
Big Induction Thingy

The guy introduced Sequent Calculus as a method to study [[Natural Deduction]]

[[Hilbert Style Proofs]] are a mathematically simple model, while [[Natural Deduction]] proofs are closer in spriti to teh proofs written by humans.
The goal of Sequent Calculus is to be a more adequate tool for proof construction than natural deductions by getting rid of elimination rules. This makes sure that if you read the proof bottom-up, the more complex formulas are always derived from more simpler ones.
```

```ad-note
title:Definition
A _sequent_ is a pair $(\Gamma,\Delta)$ where $\Gamma$ and $\Delta$ are finite sequences for formulae called _antecedent_ and _succedent_ respectively, we also write it as $\Gamma\vdash\Delta$


```

The intuitive meaning of $\Gamma\vdash\Delta$ is that the conjunctions of all the formulas in $\Gamma$ implies the disjunction of all formulas in $\Delta$.

The rules for *Sequent Calculus* are
![[Pasted image 20231023130255.png]]
```ad-seealso
title: Logics that can be expressed using Sequent Calculus
Adding restriction or getting rid of the rules changes the logic that is being used by the calculus, for example
- Enforcing that $|\Delta|\le 1$ makes this _intuitionistic_ logic
- Enforcing that $|\Delta|=1$ makes it _minimal_ logic
- Enforcing that $|\Delta|\ge 1$ makes it _Pierce Type_ logic
- Getting rid of the contraction rules makes it _linear_ logic and so on
```



---
# References
