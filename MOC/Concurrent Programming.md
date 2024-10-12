---
tags:
  - MOC
sticker: lucide//map-pin
---
# Concurrent Programming
---
## About

The spread of multiprocessor architectures has had a pervasive effect on how we develop software. 

During the twentieth century, advances in technology brought regular increases in clock speed, so software would effectively “speed up” by itself over time. In this century, however, that “free ride” has come to an end. 

Today, advances in technology bring regular increases in parallelism, but only minor increases in clock speed. Exploiting that parallelism is one of the outstanding challenges of modern computer science. 

There are easy to specify shared object that cannot be implemented by any algorithm and thus it is important to study fundamental limitations of the computations models.

Correct of concurrent programs is important in understanding that.

In the context of multiprocessor programs, not only safety, but liveness also becomes an important property to consider, and requires a different toolset from their sequential counterparts, even for informal reasoning.

This section discusses how to safely write concurrent programs.

--- 
## Notes
- [[Motivation for Concurrency Theory]]
- [[Amdahl's Law]]
- [[Atomization of Programs]]
	- [[Mutual Exclusion]]
	- [[Deadlock-freeness]]
	- [[Starvation-freeness]]
	- [[Filter Lock]]
	- [[Lamport's Bakery Lock]]
	- [[TAS Lock]]
	- [[TTAS Lock]]
	- [[Backoff Lock]]
	- [[Anderson's Lock]]
	- [[CLH queue Lock]]
- [[Bounded Wait-freeness]]
- [[Lower Bound on Shared Process]]
	- [[Proof for Lower Bound on Shared Processes]]
- [[Spin Locks]]
	- [[TAS Lock]]
	- [[TTAS Lock]]
	- [[Backoff Lock]]
- [[Queue Based Locks]]
	- [[Anderson's Lock]]
	- [[CLH queue Lock]]
- [[Semaphores]]
- [[History(Concurrent Programming)]]
- [[Concurrent Registers]]
- [[Consensus]]
	- [[Consensus Number of Atomic Read Write Registers - 1]]
	- [[Consensus Number of Atomic Read Write Registers and Atomic Queue - 2]]
	- [[Consensus Number for Compare and Set - Omega]]
- [[Universality of Concurrent Object Class]]

--- 
## MOCs

---
# References