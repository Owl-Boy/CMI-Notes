---
tags:
  - Note
  - Incomplete
---
202310171510

Tags : [[Logic]]

---
# Even is not FO-definable
We want to prove that "the size of this set is even" is not FO-definable.
Suppose we have a linear order on our sets of elements $A,B$.
$A$ has $6$ elements, $B$ has $5$.
Now, if the number of rounds is greater than $log(n)$, the spoiler has a winning strategy using binary search:

```ad-success
title: Strategy for Spoiler

- S picks the third element in $B$.
D should pick either the third or fourth element, say third in $A$, in response.
- S picks the last element in $B$.
D is forced to pick the last element in $A$ in response.
- S picks the fourth element in $B$.
D should pick fourth or fifth element, say fifth.
- S picks the fourth element in $A$, and D has no response to it.

Spoiler wins! ❇️
```


---
# References
[[First Order Logic]]
[[FOL Inexpressibility]]
[[Ehrenfeucht-Fraisse Games Proof]]