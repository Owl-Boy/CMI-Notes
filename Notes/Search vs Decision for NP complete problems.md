---
tags:
  - Note
  - Incomplete
---
202402131302

Tags : [[Complexity Theory]]
# Search vs Decision for NP complete problems
---
If we had $FACTOR$ as an oracle, we could solve integer factorisation in poly-time (in $\log n$, the size of the input).
So given the decision version, we can solve the search version in this case. But we don't know whether Int-Fact is NP-complete??

But for every NP-complete problem, search always reduces to decision.

---
Search vs Decision for $NP-$complete problems
SAT we can do.
Vertex Cover also we can do.

Can we give a general argument for all NP-complete problems?
Yes
Proof:
A is an NP complete problem.
R(x,y) is the certificate. WLOG y is in binary.
Now fix each prefix of y and ask the predicate:
$A'=\{ (x,y): y'\text{ is a prefix of }y\in\{ 0,1 \}^{p(|x|)}, R(x,y) \}$
A' is in NP, and A can be reduced to A', so NP-complete.
So the obvious algo works.


---
# References
