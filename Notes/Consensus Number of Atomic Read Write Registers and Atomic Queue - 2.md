---
tags:
  - Note
  - Incomplete
---
202409262309

Tags : [[Concurrent Programming]]
# Consensus Number of Atomic Read Write Registers and Atomic Queue
---
>[!idea] Claim
>There is a wait-free consensus solutions based on atomic queues for 2 threads.

***Pseudo Code***
```
i :  Thread value
vi: input for thread i


Q <- < Win, Lose >

Thread:
	Preferred[i] = vi
	res = Q.pop()
	if res = Win:
		decide(preferred[self])
	else:
		decide(preferred[other])
```

***Proof***

This algorithm works as one of the thread is the winner and the other one is loser. If the winner thread gets their decision after they put their value in the array, hence they can safely access it. The loser thread gets their value after the winner thread, so it can also access it safely.

---

>[!error] Claim
>There is no wait-free boolean consensus algorithm for 3 threads that uses atomic variables and an atomic queue.

The Proof a similar case bash
- If both operations are deque then the operations are commutative.
- If one operations is dequeue, one is enqueue, then the operations are commutative if they queue is non-empty. If the queue is empty, then do follow the same idea as case 2 in [[Consensus Number of Atomic Read Write Registers - 1]]
- If both options are enqueue
	- If they enqueue the same value then the operations commutative.
	- Let the queue contain $q$ elements. If any of the threads do not dequeue $q$ elements then all dequeues will be the same and hence the same execution can have from both branches.
	- >[!todo]
	> Finish later

---
# References
