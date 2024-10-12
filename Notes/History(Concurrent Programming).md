---
tags:
  - Note
  - Incomplete
---
202409120309

Tags : [[Concurrent Programming]]
# History(Concurrent Programming)
---
>[!definition] Representation of Events
>The events that are relevant here are calling a method and the method returning a value, these events are represented by 
>- $c(p, x.m, v)$
>	- This means that the method $m$ is called on object $x$ on thread $p$ with $v$ as its input value
>- $r(p, x.m, v)$
>	- This means that the method $m$ that was called on object $x$ from thread $p$ returns $v$ as its result

A history is a sequence of events. A method execution runs from its call to the first return on the same thread.

---
# References
