---
tags:
  - Note
---
202408092008

Tags : [[Concurrent Programming]]
# Amdahl's Law
---
## Harsh Realities for Parallelization
In an ideal world, upgrading from a single thread processor, to a multi thread processors with $n$ threads, should lead to an $n$-fold increase in speed. This does not happen because it is generally not easy to equally distribute a task between all threads.

>[!example] Room Painting
>Say five friends decide to pair a five-room house. If all the rooms are of the same size, then it makes sense to assign each friend to a room, and assuming everyone paints at the same rate, the job of painting the house is done five times as fast.
>
>But if one of the rooms is twice as big, then the overall time to complete the task would be significantly more inefficient since the larger room will be a bottle neck, leading to a situation where after a point exactly one of the friends would be working.

This idea is captured by Amdahl's law, which states that, given an $n$ thread processor and task which takes $1$ time unit for a single thread processor where a fraction $p$ can be done in parallel, then the time taken to complete the task would be 

$$
1 - p + \frac{p}{n}
$$

>[!theorem] Amdahl's Law
>Amdahl's Law states that the maximum speedup (i.e ratio between time taken for single threaded process an the multi threaded process is)
>$$
>S = \frac{1}{1-p + \frac{p}{n}}
>$$

>[!example] Room Painting : Continued
>For our room painting example, say that each small room is worth 1 unit, while the big room is worth 2 units. Then 5 units can be working on together. I.e $p = \frac{5}{6}$ so we get
>$$
>S = \frac{1}{1-p+\frac{p}{n}} = \frac{1}{\frac{1}{6}+\frac{1}{6}}=3
>$$

The Law tell us that If we parallelize 90% of the task to 10 threads, it will only lead to a roughly 5 fold speedup.

Considering the [[Motivation for Concurrency Theory|Counter]] example, this means that if we want the update and return to happen concurrently, this will lead to significant loss in performance.

---
# References
