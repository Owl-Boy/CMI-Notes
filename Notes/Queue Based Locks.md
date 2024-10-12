---
tags:
  - Note
---
202408282008

Tags : [[Concurrent Programming]]
# Queue Based Locks
---
[[TAS Lock]] and its variation are not feasible because of a "fight" that happens that is wasteful of resources.

One way to deal with it is to form a queue of all the threads that want the lock and provide them with it in that order.
Only the head of the queue is allowed to get the lock and when it is done with its critical section it unlocks by popping off the queue. 

These methods avoid the pitfalls of [[Spin Locks]] by having each thread spin different variables to reduce cache traffic.

A queue also provides fairness of "first-come-first-serve" at the level of the [[Lamport's Bakery Lock]].

The following are 2 implementations of queue based locks, one of them is easy, while the other one is much more portable and requires much less resources to run.
- [[Anderson's Lock]]
- [[CLH queue Lock]]

---
# References
